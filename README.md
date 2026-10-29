# Apple Stock Data Analysis & Financial Metrics (2023-2024)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

โปรเจกต์วิเคราะห์ข้อมูลทาง องการเงินและราคาหุ้นของบริษัท Apple Inc. (AAPL) ด้วยภาษา Python โดยดึงข้อมูลย้อนหลังผ่าน API เพื่อศึกษาพฤติกรรมราคา, คำนวณผลตอบแทนรายวัน (Daily Return), วัดความผันผวน, และแสดงผลในรูปแบบกราฟวิเคราะห์แนวโน้ม

## 🚀 Features
- 📊 ดึงข้อมูลราคาหุ้นย้อนหลังแบบอัตโนมัติด้วยไลบรารี `yfinance`
- 📈 คำนวณสถิติสำคัญ เช่น ราคาเปิด-ปิดเฉลี่ย, ราคาสูงสุด-ต่ำสุด และปริมาณการซื้อขายเฉลี่ย
- 📉 วิเคราะห์ความเสี่ยงและผลตอบแทน (Average Return & Standard Deviation)
- 📊 แสดงผลกราฟเชิงวิเคราะห์ 4 รูปแบบ (Closing Price Over Time, Trading Volume, Daily Returns Distribution และ Price Trend)

## 🛠️ Tech Stack
- **Language:** Python 3.9+
- **Libraries:**
  - `yfinance` (สำหรับดึงข้อมูลหุ้น)
  - `pandas` & `numpy` (สำหรับการจัดการและคำนวณข้อมูลทางสถิติ)
  - `matplotlib` (สำหรับการสร้างกราฟแสดงผล)

## ⚙️ Getting Started

### Prerequisites
ตรวจสอบให้แน่ใจว่าได้ติดตั้ง Python และไลบรารีที่จำเป็นแล้ว:
```bash
pip install yfinance pandas numpy matplotlib

Installation & Running
-โคลนโปรเจกต์นี้ หรือคัดลอกโค้ดไปรันใน Jupyter Notebook / Google Colab
-รันสคริปต์เพื่อนิดดึงข้อมูลและแสดงผลการวิเคราะห์
python  Applefinance.py

📖 Usage
ตัวอย่างโค้ดส่วนหนึ่งในการดึงข้อมูลหุ้น Apple และคำนวณสถิติผลตอบแทนรายวัน

import yfinance as yf
import pandas as pd

# ดาวน์โหลดข้อมูลหุ้น Apple ตั้งแต่วันที่ 2023-01-01 ถึง 2024-01-01
df = yf.download('AAPL', start='2023-01-01', end='2024-01-01')

# คำนวณผลตอบแทนรายวัน (Daily Return)
df['Daily_Return'] = df['Close'].pct_change()
print(f'ผลตอบแทนเฉลี่ย: {df["Daily_Return"].mean() * 100:.3f}%')
print(f'ความเบี่ยงเบนมาตรฐาน (ความผันผวน): {df["Daily_Return"].std() * 100:.3f}%')
