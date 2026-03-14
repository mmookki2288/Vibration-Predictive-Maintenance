# 🛠️ AI-Powered Vibration Predictive Maintenance System
### 📈 Predictive Analytics for Industrial Motor Health based on ISO 10816-3

![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)
![XGBoost](https://img.shields.io/badge/Model-XGBoost-green.svg)
![ISO](https://img.shields.io/badge/Standard-ISO_10816--3-orange.svg)
![University](https://img.shields.io/badge/University-Burapha_University-red.svg)

## 📖 Overview
โปรเจกต์นี้เป็นระบบ **การบำรุงรักษาเชิงพยากรณ์ (Predictive Maintenance)** สำหรับเครื่องจักรในอุตสาหกรรม โดยใช้ AI ในการวิเคราะห์และทำนายระดับความรุนแรงของการสั่นสะเทือนล่วงหน้า เพื่อป้องกันการเกิดความเสียหายกะทันหัน (Breakdown) ของเครื่องจักร

## 🚀 Key Features
- **Smart Configuration:** รองรับการเลือกกลุ่มเครื่องจักร (Group 1-4) และประเภทฐาน (Rigid/Flexible) ตามมาตรฐาน ISO 10816-3
- **Precision Validation:** ระบบตรวจสอบชื่อไฟล์และตำแหน่งจุดวัด (เช่น Motor Outboard Axial) เพื่อความถูกต้องของข้อมูล
- **AI Prediction:** ใช้โมเดล **XGBoost Regression** ในการทำนายแนวโน้มค่า Amplitude ของแรงสั่นสะเทือน
- **Zone Identification:** วิเคราะห์และระบุสถานะสุขภาพเครื่องจักรเป็น Zone A (ดีเยี่ยม) ถึง Zone D (อันตราย) โดยอัตโนมัติ

## ⚙️ วิถีการทำงานของระบบ (System Workflow)
1. **Target Setting:** ระบุกลุ่มเครื่องจักรและตำแหน่งจุดวัด (เช่น Axial/Horizontal) เพื่อกำหนดเกณฑ์ ISO
2. **Data Validation:** นำเข้าไฟล์เซนเซอร์ (.txt) และตรวจสอบความถูกต้องของชื่อไฟล์ก่อนประมวลผล
3. **Feature Engineering:** สร้างชุดข้อมูลย้อนหลัง (Lag Features) และค่าทางสถิติเพื่อให้ AI เห็นแนวโน้มการสั่น
4. **AI Processing:** ใช้ XGBoost ประมวลผลและทำนายค่าแรงสั่นสะเทือนล่วงหน้าจากข้อมูลประวัติ
5. **Result Dashboard:** แสดงผลผ่านกราฟและระบุ Zone สถานะสุขภาพเครื่องจักรเพื่อให้วิศวกรตัดสินใจได้ทันที

## 🌟 ประโยชน์และความสำคัญ (Benefits)
- **ลดค่าใช้จ่าย (Cost Reduction):** ช่วยลดงบประมาณในการซ่อมแซมด่วนและค่าอะไหล่โดยไม่จำเป็น
- **ลด Downtime:** วางแผนหยุดเครื่องจักรเพื่อซ่อมบำรุงได้ล่วงหน้า ไม่กระทบสายการผลิต
- **ความปลอดภัย (Safety):** ป้องกันอุบัติเหตุร้ายแรงจากเครื่องจักรหมุนความเร็วสูงที่อาจชำรุดขณะทำงาน
- **ยืดอายุเครื่องจักร:** การควบคุมแรงสั่นให้อยู่ในเกณฑ์ดีช่วยลดการสึกหรอของลูกปืนและซีลภายใน
- **การตัดสินใจที่แม่นยำ:** เปลี่ยนจากการใช้ความรู้สึกมาเป็นการใช้ข้อมูล AI และมาตรฐานสากล (ISO)

## 🛠️ Technology Stack
- **Language:** Python
- **AI Model:** XGBoost (Extreme Gradient Boosting)
- **Data Processing:** Pandas, NumPy, Scikit-learn
- **Visualization:** Matplotlib, Seaborn
- **Environment:** Google Colab / GitHub Integration

## 📊 Evaluation Criteria (ISO 10816-3)
- ✅ **Zone A:** เครื่องจักรใหม่/สภาพดีเยี่ยม
- ⚠️ **Zone B:** สภาพยอมรับได้ ใช้งานได้ปกติ
- 🟠 **Zone C:** เริ่มผิดปกติ ควรวางแผนซ่อมบำรุง
- ❌ **Zone D:** อันตรายมาก เครื่องอาจเสียหายได้ทุกเมื่อ

---
**Created by:** mmookki2288  
**Department:** AI & Data Science, Burapha University  

