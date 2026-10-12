# Adaptive Detection of Fake Wi-Fi Networks using Signal and Identity Analysis

A cybersecurity tool that detects Evil Twin and Rogue Access Point attacks by analyzing Wi-Fi identity (SSID/BSSID), signal strength, and authentication behavior, using K-Means clustering and rule-based risk scoring.

## Features
- Scans nearby Wi-Fi networks and collects SSID, BSSID, signal strength, authentication, encryption, channel and network type
- K-Means clustering (with StandardScaler) to classify networks as Safe or Malicious, with a confidence value
- Rule-based risk scoring (open/WEP networks, duplicate SSIDs, randomized MACs, ad-hoc networks, unusually strong signal)
- Vendor identification using an OUI database
- Automated TXT and JSON report export
- Watch mode that rescans continuously and alerts on new suspicious access points

## Project Structure
| File | Purpose |
|---|---|
| `dataset_generator.py` | Generates a synthetic Wi-Fi dataset (safe, evil twin, open rogue, WEP, ad-hoc) |
| `train_model.py` | Trains the K-Means model and saves the `.pkl` files |
| `project.py` | Main program: scanning, analysis, reports |
| `wifi_dataset.csv` | Generated dataset |
| `kmeans_model.pkl`, `scaler.pkl`, `malicious_cluster.pkl` | Saved model files |

## How to Run
```
pip install pandas numpy scikit-learn
python dataset_generator.py
python train_model.py
python project.py
```
Run `project.py` on Windows with Wi-Fi turned on, since it uses the `netsh` command.

## Tech Stack
Python, Pandas, NumPy, Scikit-learn, K-Means
