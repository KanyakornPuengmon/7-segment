# กิจกรรมที่ 1 เรื่อง การแสดงผล 0-9 
### อุปกรณ์
1. บอร์ด ESP32
2. สายจั๊ม
3. สาย Micro USB 

### ขั้นตอนการทดลอง
1. เปิดโปรแกรม Arduino IDE
2. ไปที่ Tool ตั้งค่าบอร์ดเป็น ESP32-WROOM-DA และตรวจสอบ port ที่เสียบเข้ากับคอมพิวเตอร์

![image](https://github.com/user-attachments/assets/2a4eb791-96ba-49bc-8d46-4612c2ad34f2)


3. นำโค้ดไปใส่ในโปรแกรม Arduino IDE ดังนี้

```
// 1 = LED ติด, 0 = LED ดับ (เรียงตาม segment: a, b, c, d, e, f, g)
boolean num[10][7] = {
    {1, 1, 1, 1, 1, 1, 0}, // 0
    {0, 1, 1, 0, 0, 0, 0}, // 1
    {1, 1, 0, 1, 1, 0, 1}, // 2
    {1, 1, 1, 1, 0, 0, 1}, // 3
    {0, 1, 1, 0, 0, 1, 1}, // 4
    {1, 0, 1, 1, 0, 1, 1}, // 5
    {1, 0, 1, 1, 1, 1, 1}, // 6
    {1, 1, 1, 0, 0, 1, 0}, // 7
    {1, 1, 1, 1, 1, 1, 1}, // 8
    {1, 1, 1, 1, 0, 1, 1}  // 9
};

// กำหนดขา GPIO สำหรับ 7-segment (เรียงตาม: a, b, c, d, e, f, g)
int segmentPins[7] = {5, 16, 17, 18, 19, 21, 22};

void setup()
{
  pinMode(5, OUTPUT);
  pinMode(16, OUTPUT);
  pinMode(17, OUTPUT);
  pinMode(18, OUTPUT);
  pinMode(19, OUTPUT);
  pinMode(21, OUTPUT);
  pinMode(22, OUTPUT);

}

void loop() {
    // แสดงตัวเลข 0-9 วนลูป
    for (int i = 0; i < 10; i++) {
        show_num(i);   // แสดงตัวเลขปัจจุบัน
        delay(1000);   // รอ 1 วินาที
    }
}

// ฟังก์ชันสำหรับแสดงตัวเลขบน 7-segment
void show_num(int numshow) {
    for (int i = 0; i < 7; i++) {
        digitalWrite(segmentPins[i], num[numshow][i]);
    }
}
```

4. นำสายจั๊มมาต่อ 7 segment เข้ากับ บอร์ด ESP32 ดังนี้

![image](https://github.com/user-attachments/assets/ba4329a3-de90-48d4-aa39-108d35b4d373)

5. เสียบสาย Micro USB เข้ากับคอมพิวเตอร์และ ESP32
6. กด save
7. กด verify
8. กด upload พร้อมกดปุ่ม boot จนกว่าจะ upload เสร็จ

#
#
#
#
#

#

# กิจกรรมที่ 2 เรื่อง การกดเพิ่ม - ลดเลข
### อุปกรณ์
1. บอร์ด ESP32
2. สายจั๊ม
3. สาย Micro USB 

### ขั้นตอนการทดลอง
1. เปิดโปรแกรม Arduino IDE
2. ไปที่ Tool ตั้งค่าบอร์ดเป็น ESP32-WROOM-DA และตรวจสอบ port ที่เสียบเข้ากับคอมพิวเตอร์

![image](https://github.com/user-attachments/assets/2a4eb791-96ba-49bc-8d46-4612c2ad34f2)


3. แก้ไขโค้ดในโปรแกรม Arduino IDE ดังนี้


    3.1 เพิ่มปุ่ม 2 ปุ่มโดยกำหนด ดังนี้
   
   
   ![image](https://github.com/user-attachments/assets/20e2bf79-4165-461b-b582-317d531aaa5c)


    3.2 จากนั้นแก้ไข code ในการแสดงเงื่อนไข
   
    
![image](https://github.com/user-attachments/assets/6438e7eb-ed68-44d2-9d8a-c7744b2b06f2)


4. นำสายจั๊มมาต่อ 7 segment เข้ากับ บอร์ด ESP32 ดังนี้


![image](https://github.com/user-attachments/assets/2c75bf05-5e98-4481-b3ad-d4d95f2ab4bd)


5. เสียบสาย Micro USB เข้ากับคอมพิวเตอร์และ ESP32
6. กด save
7. กด verify
8. กด upload พร้อมกดปุ่ม boot จนกว่าจะ upload เสร็จ
    
