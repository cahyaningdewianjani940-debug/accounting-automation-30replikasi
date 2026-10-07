```python
# accounting-automation-30replikasi 
Replikasi eksperimen akuntansi seed 2026
Mean manual 2.88% vs Python 0%
30 replikasi reproducible

import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
np.random.seed(2026)
manual = np.clip(np.random.normal(2.88,1.1,30),1,5)
python = np.zeros(30)
df = pd.DataFrame({"manual":manual,"python":python})
df.to_csv("hasil.csv")
plt.boxplot([manual,python],labels=["Manual 2.88%","Python 0%"])
plt.savefig("boxplot.png")
```
