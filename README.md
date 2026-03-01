# 透過 CNN 卷積神經網路對心電圖心律不整進行分類 
### Classifying ECG Arrhythmia using CNN and Recurrence Plot (RP)

![License](https://img.shields.io/badge/license-MIT-green.svg) 
![Python](https://img.shields.io/badge/python-3.8%2B-blue.svg)
![TensorFlow](https://img.shields.io/badge/framework-TensorFlow%20/%20Keras-orange.svg)

## 📌 專案背景
心血管疾病 (CVD) 佔全球死亡人數的 31%，是現代人重大的健康威脅。本研究旨在利用深度學習技術，將傳統的一維心電圖 (ECG) 信號轉換為二維影像特徵，藉此提升機器辨識心律不整的準確率，輔助醫師進行臨床診斷。

## 🚀 技術核心：遞歸圖 (Recurrence Plot)
本專案不直接處理一維信號，而是採用 **非線性動力學** 中的遞歸圖技術。
- **原理**：將 ECG 信號投射至高維相空間，計算軌跡點之間的距離，生成對稱的二維矩陣圖。
- **優勢**：RP 圖能有效捕捉 ECG 信號中的非平穩性與拓撲結構特徵，使 CNN 能夠像辨識人臉一樣辨識心律不整。



## 🛠 系統架構
1. **數據獲取**：使用 PhysioNet 公開資料庫。
2. **預處理**：信號去噪、R波檢測、擷取 2 秒長度的節拍。
3. **特徵轉換**：將 1D ECG 轉換為 2D Recurrence Plot (RP) 影像。
4. **模型訓練**：使用 **CNN (Convolutional Neural Network)** 進行特徵提取與分類。



## 📂 資料夾結構
```text
├── src/                # 核心程式碼
│   ├── preprocess.py   # 資料預處理與信號清理
│   ├── rp_transform.py # 1D 信號轉 2D RP 圖腳本
│   └── train_cnn.py    # CNN 模型定義與訓練
├── paper/              # 學士論文全文 (PDF)
├── images/             # README 使用的圖表與實驗截圖
├── requirements.txt    # 專案環境依賴套件
└── README.md           # 專案說明文件
