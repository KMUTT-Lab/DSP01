# 🎛️ DSP Lab 1: First Contact & The Building Blocks (Hello DSP!)

ยินดีต้อนรับสู่ Lab สัปดาห์แรกของการเรียนรู้ Digital Signal Processing (DSP) ด้วย Python! 
ใน Lab นี้เราจะเริ่มต้นจากการทำความรู้จักเครื่องมือ สร้างสัญญาณพื้นฐานด้วยมือของเราเอง และเรียนรู้ว่าสัญญาณในโลกแห่งความเป็นจริงนั้นหน้าตาเป็นอย่างไร

## 🎯 วัตถุประสงค์การเรียนรู้ (Learning Objectives)
1. สามารถใช้งาน Google Colab และ Library พื้นฐาน (`numpy`, `matplotlib`) ได้
2. เข้าใจและสามารถเขียนโค้ดเพื่อสร้างสัญญาณพื้นฐาน (Sine Wave, Square Wave) ได้
3. เข้าใจแนวคิดของ Sampling Rate และผลกระทบต่อสัญญาณดิจิทัล
4. สามารถจำลองสัญญาณรบกวน (Noise) และรวมเข้ากับสัญญาณหลักได้

## 🛠️ สิ่งที่ต้องเตรียมพร้อม (Prerequisites)
- บัญชี Google Account (สำหรับการเข้าใช้ Google Colab)
- ความรู้พื้นฐานภาษา Python (Variables, Loops, Functions)

## 📝 ขั้นตอนการปฏิบัติงาน (Standard Operating Procedure - SOP)

**Phase 1: การเตรียม Environment**
1. คลิกที่ปุ่มด้านล่างเพื่อเปิดไฟล์ Jupyter Notebook ของ Lab นี้บน Google Colab
   [![Open In Colab](https://colab.research.google.com/github/KMUTT-Lab/DSP01/blob/main/Lab01_HelloDSP.ipynb)]
2. เมื่อหน้า Colab เปิดขึ้นมา ให้คลิกที่เมนู `File` > `Save a copy in Drive` เพื่อสร้างสำเนาเป็นของตัวเอง
3. เปลี่ยนชื่อไฟล์สำเนาโดยเพิ่มรหัสนักศึกษาไว้ด้านหน้า เช่น `67XXXXXXX_Lab1_HelloDSP.ipynb`

**Phase 2: การทำ Lab**
1. **รันเซลล์โค้ดตามลำดับ:** ให้อ่านคำอธิบายใน Text cell และรัน Code cell ทีละบล็อก (กด `Shift + Enter`)
2. **เติมโค้ดในส่วนที่ขาดหาย:** ในไฟล์จะมีจุดที่เขียนว่า `### YOUR CODE HERE ###` ให้นักศึกษาเขียนโค้ด Python เพื่อแก้โจทย์ตามเงื่อนไขที่กำหนด
3. **สังเกตผลลัพธ์:** ตรวจสอบกราฟและฟังเสียงที่ได้จากการรันโค้ด หากเกิด Error ให้พยายามอ่าน Error Message และแก้ไข

**Phase 3: การส่งงาน (Submission)**
เมื่อทำ Lab เสร็จสิ้นและตรวจสอบผลลัพธ์เรียบร้อยแล้ว:
1. ไปที่เมนู `File` > `Save a copy in GitHub`
2. เลือก Repository ที่กำหนดให้สำหรับวิชานี้ (หากใช้ GitHub Classroom ระบบจะสร้าง Repo ไว้ให้แล้ว)
3. ในช่อง Commit message ให้พิมพ์ `Completed Lab 1`
4. ตรวจสอบในหน้า GitHub ของตนเองว่าไฟล์ถูก Push ขึ้นไปเรียบร้อยแล้ว

---
*หากมีข้อสงสัยหรือพบปัญหาทางเทคนิค สามารถเปิด Issue ในหน้า GitHub Repository ของวิชานี้ได้ทันที*