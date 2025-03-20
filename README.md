# Fraud-Detection
To detect fault transaction using Python
from sklearn.ensemble import IsolationForest
import pandas as pd

# Sample transaction data
data = pd.DataFrame({
    'amount': [100, 200, 5000, 150, 300],
    'time': [1, 2, 3, 4, 5]
})
model = IsolationForest(contamination=0.2)
data['anomaly'] = model.fit_predict(data)
print(data[data['anomaly'] == -1])  # -1 indicates an outlier (potential fraud)
