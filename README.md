# 🎛️ DSP Lab 1: First Contact & The Building Blocks (Hello DSP!)

ยินดีต้อนรับสู่ภารกิจแรกของการเรียนรู้ Digital Signal Processing (DSP) ด้วย Python! 
ในสัปดาห์นี้เราจะมาทำลายกำแพงความกลัวคณิตศาสตร์ ทำความรู้จักเครื่องมือระดับสากล และสร้างสัญญาณคลื่นเสียงด้วยมือของคุณเอง

## 🎯 วัตถุประสงค์การเรียนรู้
1. คุ้นเคยกับสภาพแวดล้อมการเขียนโค้ดบน Google Colab และการใช้ไลบรารีพื้นฐาน (`numpy`, `matplotlib`)
2. เข้าใจและสามารถเขียนโค้ดสร้างสัญญาณ (Signal Generation) เช่น Sine Wave ได้
3. เข้าใจผลกระทบของ Sampling Rate ที่มีต่อสัญญาณดิจิทัลและเสียง
4. จำลองสัญญาณรบกวน (Noise) ในโลกความเป็นจริงได้

---

## 🚦 ลำดับขั้นตอนการทำภารกิจ (Mission Flow)

### Step 0: เตรียมฐานทัพ (Prerequisites)
หากคุณยังไม่มีบัญชี GitHub หรือยังไม่เคยสร้าง Repository สำหรับเก็บงานวิชานี้ ให้หยุดอ่านตรงนี้ แล้วไปจัดการสร้างฐานทัพให้เรียบร้อยก่อน!
👉 **[คลิกอ่านคู่มือ GitHub 101: การสร้าง Repository แรกของคุณ](./GitHub_Setup_Guide.md)**

### Step 1: เข้าสู่ระบบ (System Override)
เมื่อมี Repository ของตัวเองแล้ว ให้คลิกที่ป้ายด้านล่างนี้เพื่อดึงไฟล์ "พิมพ์เขียว" (Skeleton Code) ของ Lab 1 ไปเปิดบน Google Colab ของคุณ

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/KMUTT-Lab/DSP01/blob/main/Lab01_HelloDSP.ipynb)
*(หมายเหตุ: หากขึ้น Error ให้ตรวจสอบว่าคุณได้ Login บัญชี Google เรียบร้อยแล้ว)*

### Step 2: ปฏิบัติการ (Execution)
1. เมื่อหน้า Colab เปิดขึ้นมา ให้อ่านคำอธิบายใน **Text Cell** อย่างละเอียด
2. รัน **Code Cell** ทีละบล็อกตามลำดับจากบนลงล่าง (ใช้คีย์ลัด `Shift + Enter`)
3. ในจุดที่มีคำว่า `### YOUR CODE HERE ###` ให้คุณเติมโค้ด Python เพื่อไขปริศนาให้สมบูรณ์
4. สังเกตกราฟและเปิดลำโพงเพื่อฟังเสียงผลลัพธ์ที่คุณสร้างขึ้น!

### Step 3: การส่งมอบข้อมูล (Extraction & Submission)
เมื่อภารกิจเสร็จสิ้น กราฟแสดงผลถูกต้อง และเสียงทำงานปกติ ได้เวลาส่งงานเข้าสู่ระบบส่วนกลาง
กรุณาทำตามขั้นตอนการบันทึกไฟล์ลง GitHub และส่งลิงก์ผ่านระบบให้ถูกต้องตามมาตรฐาน
👉 **[คลิกอ่านคู่มือ SOP: ขั้นตอนการส่งงาน DSP Lab อย่างละเอียด](./Submission_SOP.md)**

---
*หากระบบขัดข้องหรือมีข้อสงสัย ให้เปิด Issue ใน GitHub Repository ของวิชานี้ หรือสอบถามในช่องทางติดต่อส่วนกลาง*

> *"The first wave is generated. The system is listening."*
> *จัดทำโดย [Living Incognito] - วิชา ICE385 COMPUTER TECHNOLOGY LABORATORY I (Introduction to Digital Signal Processing) - 13 Mar 2026*
