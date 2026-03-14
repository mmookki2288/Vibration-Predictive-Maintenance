# 🛠️ AI-Powered Vibration Predictive Maintenance System
### 📈 Predictive Analytics for Industrial Motor Health based on ISO 10816-3

![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)
![XGBoost](https://img.shields.io/badge/Model-XGBoost-green.svg)
![ISO](https://img.shields.io/badge/Standard-ISO_10816--3-orange.svg)
![University](https://img.shields.io/badge/University-Burapha_University-red.svg)

## 📖 Overview
โปรเจกต์นี้คือการพัฒนาระบบ **การบำรุงรักษาเชิงพยากรณ์ (Predictive Maintenance)** สำหรับเครื่องจักรหมุนในอุตสาหกรรม โดยใช้โมเดล AI ในการวิเคราะห์และทำนายระดับความรุนแรงของการสั่นสะเทือนล่วงหน้า เพื่อเปลี่ยนจากการซ่อมเมื่อพัง (Reactive) เป็นการซ่อมก่อนเสียหาย (Predictive) ตามมาตรฐานสากล

---

## 🔍 Data Structure & Extraction (การวิเคราะห์ข้อมูล)
ระบบได้รับการออกแบบให้มี **Automated Parsing** เพื่อดึงข้อมูลสำคัญจากไฟล์รายงาน (.txt) มาใช้งานโดยอัตโนมัติ:

<img width="494" height="131" alt="Image" src="https://github.com/user-attachments/assets/a68e2a16-8f22-49db-9bb5-79c2ec5c1849" />

### 📊 ตารางสรุปการสกัดข้อมูล (Data Mapping Table)

| ข้อมูลในไฟล์ | ตัวอย่างจากภาพ | การประมวลผลในโค้ด | ประโยชน์ในโปรเจกต์ |
| :--- | :--- | :--- | :--- |
| **Equipment** | `Cooling Pump` | **Regex Extraction** | ตรวจสอบความถูกต้องของชื่อเครื่องจักร (Validation) |
| **Meas. Point** | `M1H (Horizontal)` | **Metadata Matching** | ระบุทิศทางเพื่อเลือกเกณฑ์ **ISO 10816-3** ที่ถูกต้อง |
| **Date/Time** | `28-Jun-24 08:19:52`| **Datetime Indexing** | จัดเรียงลำดับเวลาเพื่อวิเคราะห์แนวโน้ม (Time-series) |
| **Amplitude** | `Acceleration in G-s` | **Data Normalization** | แปลงค่าดิบให้เป็นหน่วยที่ AI พร้อมนำไปประมวลผล |

---

## 🚀 Key Features
- **Smart Configuration:** เลือกกลุ่มเครื่องจักร (Group 1-4) และประเภทฐาน (Rigid/Flexible) ได้ตามจริงตามมาตรฐาน ISO
- **Precision Validation:** ระบบตรวจเช็กชื่อไฟล์อัตโนมัติ ป้องกันการนำข้อมูลผิดตำแหน่งมาวิเคราะห์ (Anti-Human Error)
- **AI Prediction:** ใช้โมเดล **XGBoost Regression** พยากรณ์ค่าแนวโน้มแรงสั่นสะเทือนในอนาคตได้อย่างแม่นยำ
- **Zone Identification:** สรุปสถานะสุขภาพเครื่องจักรแบ่งตาม **Zone A, B, C, D** ทันทีเพื่อให้ตัดสินใจได้ง่าย

## ⚙️ วิถีการทำงานของระบบ (System Workflow)
1. **Target Setting:** กำหนดคุณสมบัติเครื่องจักรเพื่อเลือกเกณฑ์ ISO ที่เหมาะสม
2. **Data Validation:** นำเข้าไฟล์ (.txt) และตรวจสอบ Metadata (ชื่อเครื่อง/จุดวัด) เพื่อความถูกต้อง
3. **Feature Engineering:** สร้าง Lag Features เพื่อให้ AI เรียนรู้รูปแบบความสัมพันธ์ของเวลาและแนวโน้ม
4. **AI Processing:** ประมวลผลด้วย XGBoost เพื่อพยากรณ์ค่าความรุนแรงของการสั่นสะเทือนในอนาคต
5. **Result Dashboard:** แสดงผลผ่านกราฟและระบุโซนความเสี่ยงเพื่อให้วิศวกรวางแผนซ่อมบำรุงได้ทันท่วงที

## 🌟 ประโยชน์และความสำคัญ (Benefits)
- **Cost Reduction:** ลดค่าใช้จ่ายในการซ่อมแซมด่วนและค่าอะไหล่สำรองที่ไม่ได้วางแผนไว้
- **Minimize Downtime:** วางแผนหยุดเครื่องจักรล่วงหน้าได้ (Planned Maintenance) ไม่กระทบสายการผลิต
- **Safety First:** ลดความเสี่ยงอุบัติเหตุร้ายแรงจากเครื่องจักรหมุนความเร็วสูงที่อาจชำรุดขณะทำงาน
- **Asset Longevity:** ช่วยยืดอายุการใช้งานของลูกปืน (Bearings) และเพลาจากการดูแลแรงสั่นให้อยู่ในเกณฑ์ดี
- **Data-Driven Decision:** ตัดสินใจบนพื้นฐานของข้อมูล AI และมาตรฐานสากลแทนการใช้ดุลพินิจส่วนบุคคล

## 🛠️ Technology Stack
- **Language:** Python
- **AI Model:** XGBoost (Extreme Gradient Boosting)
- **Libraries:** Pandas, NumPy, Scikit-learn, Matplotlib, Seaborn
- **Platform:** Google Colab / GitHub Integration

## 📊 Evaluation Criteria (ISO 10816-3)
- ✅ **Zone A:** เครื่องจักรใหม่/สภาพดีเยี่ยม (Good)
- ⚠️ **Zone B:** สภาพยอมรับได้ ใช้งานได้ปกติ (Satisfactory)
- 🟠 **Zone C:** เริ่มผิดปกติ ควรหาเวลาวางแผนซ่อม (Unsatisfactory)
- ❌ **Zone D:** อันตรายมาก ต้องหยุดเครื่องทันที (Unacceptable)

---
**Created by:** mmookki2288  
**Department:** AI & Data Science, Burapha University  
**Presentation Date:** March 18, 2026
