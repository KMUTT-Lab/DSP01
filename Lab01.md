# 🎛️ Lab 1: First Contact & The Building Blocks (Hello DSP!)

ภารกิจในสัปดาห์นี้คือการทำความเข้าใจว่าคอมพิวเตอร์สร้างและมองเห็น "เสียง" ได้อย่างไร คุณจะได้สร้างคลื่นเสียงของตัวเองและจำลองสัญญาณรบกวน (Noise) ในโลกความเป็นจริง

**ข้อควรระวัง:** รันโค้ดทีละเซลล์จากบนลงล่าง และเติมโค้ดในบรรทัดที่มีคำว่า `### YOUR CODE HERE ###`

---

### **[Code Cell] Phase 1: เตรียมเครื่องมือ (The Toolkits)**

```python
# Import ไลบรารีที่จำเป็นสำหรับภารกิจนี้
import numpy as np                  # สำหรับจัดการข้อมูลตัวเลขและอาร์เรย์ (Array)
import matplotlib.pyplot as plt     # สำหรับวาดกราฟ
from IPython.display import Audio   # สำหรับสร้างเครื่องเล่นเสียงใน Colab

print("Libraries imported successfully! พร้อมลุยภารกิจต่อไป")

```

---

## ภารกิจที่ 1: สรรค์สร้างเวลา (Time Vector)

สัญญาณดิจิทัลคือข้อมูลที่ถูกเก็บเป็น "จุด" ต่อเนื่องกันไปตามเวลา สิ่งแรกที่เราต้องทำคือการสร้าง "แกนเวลา (Time Axis)" ขึ้นมา

* **Sampling Rate ($f_s$):** จำนวนจุดข้อมูลใน 1 วินาที (มาตรฐานแผ่นซีดีคือ 44,100 จุด/วินาที)
* **Duration:** ความยาวของเสียงที่เราต้องการ (วินาที)

---

### **[Code Cell]**

```python
fs = 44100          # Sampling Rate: 44100 Hz
duration = 1.0      # ความยาวเสียง: 1 วินาที
num_samples = int(fs * duration) # จำนวนจุดข้อมูลทั้งหมด

# MISSION 1: สร้าง Array ของเวลา 't' ตั้งแต่ 0 ถึง 1 วินาที
# Hint: ใช้ฟังก์ชัน np.linspace(จุดเริ่มต้น, จุดสิ้นสุด, จำนวนจุด)
t = ### YOUR CODE HERE ###

print(f"สร้างแกนเวลาสำเร็จ! จำนวนจุดข้อมูลทั้งหมด: {len(t)} จุด")
print(f"ข้อมูล 5 จุดแรกคือ: {t[:5]}")

```

---

## ภารกิจที่ 2: ปลุกชีพเสียง (Signal Generation)

เมื่อเรามีเวลาแล้ว ต่อไปเราจะสร้าง "คลื่น" (Wave) ขึ้นมาเกาะบนแกนเวลานั้น
สมการทางคณิตศาสตร์ของคลื่นเสียง (Sine Wave) พื้นฐานคือ:


$$y(t) = A \cdot \sin(2 \cdot \pi \cdot f \cdot t)$$

* $A$ = แอมพลิจูด (ความดัง)
* $f$ = ความถี่ (ระดับเสียงแหลม/ทุ้ม หน่วยเป็น Hz)

---


```python
f = 440.0   # ความถี่ 440 Hz (เสียงโน้ต A4 หรือเสียงตั้งสายกีตาร์)
A = 1.0     # แอมพลิจูดสูงสุด (ความดัง)

# MISSION 2: แปลงสมการคณิตศาสตร์ด้านบนให้เป็นโค้ด Python
# Hint: ค่า pi ใช้ np.pi และฟังก์ชัน sin ใช้ np.sin()
y = ### YOUR CODE HERE ###

# มาดูกราฟหน้าตาคลื่นที่เราสร้างขึ้น (พล็อตแค่ 0.01 วินาทีแรกให้เห็นคลื่นชัดๆ)
plt.figure(figsize=(10, 4))
plt.plot(t[:441], y[:441], color='blue') # 441 จุด = 0.01 วินาที
plt.title("My First Sine Wave (440 Hz)")
plt.xlabel("Time (Seconds)")
plt.ylabel("Amplitude")
plt.grid(True)
plt.show()

```

---


## ภารกิจที่ 3: เปิดโสตประสาท (Let's Hear It!)

กราฟอาจจะดูสวยดี แต่ DSP คือเรื่องของเสียง! ลองนำข้อมูล `y` ที่เราสร้างไปแปลงเป็นเสียงกันดู

---


```python
# MISSION 3: ใส่ตัวแปรคลื่นเสียงของเราลงไปในฟังก์ชัน Audio
display(Audio(data=### YOUR CODE HERE ###, rate=fs))

```

---


**🔥 Mini-Challenge:** ลองย้อนกลับไปเปลี่ยนค่าความถี่ `f` ในภารกิจที่ 2 ให้เป็น `880` (เสียงสูงขึ้น) หรือ `220` (เสียงต่ำลง) แล้วรันเซลล์ใหม่ลงมาเรื่อยๆ เพื่อฟังความแตกต่าง!

---


## ภารกิจที่ 4: โลกแห่งความเป็นจริงย่อมมีรอยด่างพร้อย (Adding Noise)

ในโลกความเป็นจริง สัญญาณแทบทุกชนิดมี "สัญญาณรบกวน" (Noise) ปะปนอยู่เสมอ เช่น เสียงซ่าจากไมโครโฟน หรือคลื่นแทรก เราจะมาลองสร้าง White Noise แล้วนำมาผสมกับเสียงเดิมกัน

---


```python
# สร้าง White Noise (สัญญาณสุ่มแบบ Gaussian distribution)
noise_amplitude = 0.3 # ปรับความดังของ Noise
noise = noise_amplitude * np.random.normal(0, 1, len(t))

# MISSION 4: นำสัญญาณต้นฉบับ (y) มาบวกกับสัญญาณรบกวน (noise)
y_noisy = ### YOUR CODE HERE ###

# วาดกราฟเปรียบเทียบ
plt.figure(figsize=(10, 4))
plt.plot(t[:441], y_noisy[:441], color='red', alpha=0.7, label='Noisy Signal')
plt.plot(t[:441], y[:441], color='blue', label='Original Signal')
plt.title("Clean vs Noisy Signal")
plt.xlabel("Time (Seconds)")
plt.ylabel("Amplitude")
plt.legend()
plt.grid(True)
plt.show()

# ฟังเสียงที่โดน Noise รบกวน
print("เสียงที่ปนเปื้อน Noise:")
display(Audio(data=y_noisy, rate=fs))

```

---

