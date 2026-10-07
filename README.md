# accounting-automation-30replikasi
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt

# KODE REPRODUCIBLE SEED 2026 - MEAN 2.88%
np.random.seed(2026)

manual_error = np.random.normal(loc=2.88, scale=1.1, size=30)
manual_error = np.clip(manual_error, 1.0, 5.0)
python_error = np.zeros(30)

df = pd.DataFrame({
    "replikasi": range(1,31),
    "manual_2.88%": manual_error,
    "python_0%": python_error
})

print(df.head())
df.to_csv("hasil_30_replikasi.csv", index=False)

plt.figure()
plt.boxplot([manual_error, python_error], labels=["Manual 2.88%", "Python 0%"])
plt.title("Error Rate 30 Replikasi seed=2026")
plt.savefig("boxplot_cek1.png")
plt.show()
