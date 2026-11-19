# 📅 Smart Schedule (ตารางเรียนอัจฉริยะ)

> **เว็บแอปพลิเคชันตารางเรียนอัจฉริยะ พร้อม Widget หน้าจอโฮมสำหรับ Android & iOS และระบบเชื่อมต่อ Google Calendar ในคลิกเดียว**

🌐 **เข้าใช้งานผ่านเว็บไซต์:** [https://flyingtoasts.github.io/my-uni-schedule/](https://flyingtoasts.github.io/my-uni-schedule/)

---

## ✨ ฟีเจอร์หลัก (Key Features)

### 1. 📆 การจัดการตารางเรียน (Smart Timetable)
- **มุมมองหลากหลาย:** สลับดูได้ทั้ง **มุมมองรายวัน (Daily Timeline)** และ **มุมมองตารางรายสัปดาห์ (Weekly Hourly Matrix)**
- **รองรับ Section / กลุ่มเรียน:** กำหนด Sec ของแต่ละวิชาได้ชัดเจน พร้อมแสดงป้าย Sec บนการ์ดคาบเรียน
- **รองรับวิชาปฏิบัติการ (Lab):** กำหนดห้องเรียนแยกรายสัปดาห์ และระบุสัปดาห์ที่งดเรียนได้สูงสุด 25 สัปดาห์
- **รองรับวิชาเรียนหลายรอบ (Multi-session):** กำหนดรอบเรียนย่อยในสัปดาห์เดียวกันได้
- **Real-time Live Status:** แสดงสถานะ *กำลังเรียน* หรือ *คาบถัดไป* พร้อมแถบความคืบหน้า (Progress Bar) และเวลานับถอยหลังแบบสด
- **ระบบหมวดหมู่สี (Color Categories):** ปรับแต่งชื่อหมวดและโค้ดสีได้อิสระ

### 2. 📝 โน้ตรายวิชา & รายการการบ้าน (Notes & Tasks)
- บันทึกได้ 4 ประเภท: **โน้ตถาวร**, **การบ้าน/งาน**, **แจ้งงดคลาส**, และ **ประกาศทั่วไป**
- สรุปงานค้างและแจ้งเตือนวันกำหนดส่งอัตโนมัติ
- ระบบเช็คถูกเมื่อทำงานเสร็จ (Interactive Checklist)

### 3. 🎯 คำนวณเกรด & วางแผนการเรียน (GPA & Grade Projection)
- กำหนดสัดส่วนคะแนน (Weight) ในแต่ละรายวิชา (Midterm, Final, การบ้าน, โปรเจกต์ ฯลฯ)
- บันทึกคะแนนที่ได้จริง พร้อมคาดการณ์เกรดอัตโนมัติ (A, B+, B, C+...)

### 4. 🔔 ระบบเชื่อมต่อ Google Calendar & ส่งออก .ics (1-Click Google Sync)
- **1-Click Google Sign-in:** ผู้ใช้สามารถล็อกอินด้วยอีเมล Google ของตนเองได้ทันที ไม่ต้องกรอก Client ID หรือ API Key ใดๆ
- **Direct OAuth Redirect Flow:** รองรับการทำงานบนเบราว์เซอร์มือถือ (Brave, Chrome, Safari) และ Android APK โดยไม่ติดปัญหาหน้าจอขาว Popup
- **เพิ่มตารางสอบ & การบ้านลง Google Calendar:** เลือกลงปฏิทินแบบแยกรายการหรือลงทั้งหมดพร้อมกัน
- **ตรวจเช็คสถานะจริง (Real-time Status Verification):** ตรวจสอบว่ากิจกรรมยังอยู่บน Google Calendar จริงหรือไม่ พร้อมปุ่มสั่งลบออกจาก Google Calendar โดยตรง
- **ส่งออกไฟล์ .ics:** ดาวน์โหลดไฟล์ปฏิทินมาตรฐานเพื่อนำไปใช้กับ Apple Calendar, Outlook หรือแอปอื่นๆ

### 5. 💾 สำรองและกู้คืนข้อมูล (Backup & Restore)
- **ส่งออกไฟล์ JSON:** บันทึกข้อมูลตารางเรียน, ช่วงสอบ, สี และโน้ตทั้งหมดเก็บไว้เป็นไฟล์ `.json`
- **ระบบดาวน์โหลดอัจฉริยะ (Universal Download):** เมื่อเปิดในแอป Android APK จะบันทึกไฟล์เข้าโฟลเดอร์ `Downloads` ของตัวเครื่องโดยตรงผ่าน Native Bridge

### 6. 📱 วิดเจ็ตหน้าจอโฮม (Home Screen Widget)
- รองรับทั้ง **Android AppWidget** และ **iOS WidgetKit**
- แสดงวิชาที่กำลังเรียน, วิชาถัดไป พร้อมห้องเรียน เวลา และงานที่ค้างอยู่บนหน้าจอหลัก

---

## 🏗️ โครงสร้างโปรเจกต์ (Project Structure)

```text
SmartScheduleWidget/
├── index.html          # โค้ดเว็บแอปพลิเคชันหลัก (Single Page Application)
├── version.json        # ไฟล์ระบุเวอร์ชันเว็บสำหรับระบบ Auto-Update ของ Android APK
├── README.md           # เอกสารคู่มือโปรเจกต์ (มาตรฐาน GitHub)
├── read.md             # เอกสารคู่มือโปรเจกต์
├── README_TH.md        # เอกสารสรุปต้นฉบับ
├── android/            # โปรเจกต์ Android (Kotlin + WebView + AppWidget)
│   ├── app/
│   │   ├── src/main/java/com/smartclass/widget/
│   │   │   ├── MainActivity.kt           # ตัวเปิด WebView + Native Bridge + จัดการ Download
│   │   │   ├── ScheduleWidgetProvider.kt # ตัวจัดการวิดเจ็ตหน้าจอโฮม Android
│   │   │   └── UpdateCheckWorker.kt      # ตัวตรวจจับอัปเดตเวอร์ชันเว็บอัตโนมัติ
│   │   └── build/outputs/apk/debug/
│   │       └── app-debug.apk             # ไฟล์ APK พร้อมติดตั้งสำหรับทดสอบ
│   └── build.gradle.kts
└── ios/                # โปรเจกต์ iOS (Swift + WKWebView + WidgetKit)
    └── project.yml     # XcodeGen configuration
```

---

## 🚀 ขั้นตอนการติดตั้งและการนำไปใช้งาน

### 1. การอัปเดตเว็บไซต์บน GitHub Pages
1. คัดลอกไฟล์ `index.html` และ `version.json` ไปไว้ที่ Root ของ Repository `flyingtoasts/my-uni-schedule` บน GitHub
2. ทำการ Commit & Push การเปลี่ยนแปลง
3. เมื่อ GitHub Pages ทำการ Deploy เสร็จแล้ว หน้าเว็บเวอร์ชันล่าสุดจะพร้อมใช้งานทันที

### 2. การใช้งานบน Android APK
- หากติดตั้งแอป APK ไว้ในเครื่องแล้ว ตัวแอปจะดึงข้อมูลหน้าเว็บล่าสุดจาก GitHub Pages มาแสดงโดยอัตโนมัติ (สามารถปัดปิดแอปจาก Recent Apps แล้วเปิดใหม่เพื่อรีเฟรชได้ทันที)
- หากต้องการคอมไพล์ APK ใหม่ด้วยตนเอง:
  ```bash
  cd android
  ./gradlew assembleDebug
  ```
  ไฟล์ APK ที่ได้จะอยู่ที่ `android/app/build/outputs/apk/debug/app-debug.apk`

### 3. การเพิ่ม Widget บนหน้าจอโฮม (Android)
1. เปิดแอป Smart Schedule อย่างน้อย 1 ครั้ง เพื่อให้แอปซิงก์ข้อมูลตารางเรียนเข้าสู่วิดเจ็ต
2. ออกไปที่หน้าจอหลักของโทรศัพท์ กดค้างที่พื้นที่ว่าง แล้วเลือก **วิดเจ็ต (Widgets)**
3. ค้นหา **Smart Schedule** แล้วลากวิดเจ็ตมาวางที่หน้าจอ

---

## 🔒 ความปลอดภัยและความเป็นส่วนตัว (Security & Privacy)

- **ข้อมูลตารางเรียนทั้งหมดถูกเก็บไว้ในเครื่องของผู้ใช้ (Local Storage):** ไม่มีการส่งข้อมูลวิชาเรียนหรือโน้ตไปยังเซิร์ฟเวอร์ภายนอกใดๆ
- **ความปลอดภัยของ Google OAuth:**
  - ตัวแอปเชื่อมต่อกับ Google Calendar API ผ่านสิทธิ์ `calendar.events` เท่านั้น
  - การล็อกอินจะเข้าสู่บัญชีส่วนตัวของผู้ใช้แต่ละคน ข้อมูลปฏิทินจะแยกกันโดยเด็ดขาด 100%

---

## 📝 บันทึกการอัปเดต (Changelog)

- **v1.1.2:**
  - แก้ไขปัญหาข้อมูล Section (Sec) หายเมื่อปิด-เปิดแอปใหม่ โดยปรับปรุงฟังก์ชัน `sanitizeCourse` ให้เก็บรักษาฟิลด์ Section ไว้อย่างสมบูรณ์
  - เพิ่มป้ายแสดง Section บนการ์ดเรียนปัจจุบัน, คาบถัดไป, ตารางรายวัน และตารางรายสัปดาห์
  - พัฒนาระบบ `downloadFileBlob` สำหรับส่งออกไฟล์ `.json` และ `.ics` ให้ทำงานร่วมกับ `WidgetBridge.saveDownload` ของ Android เพื่อเซฟลงโฟลเดอร์ Downloads ได้ทันที
- **v1.1.1:**
  - ตัดหน้าต่างและการตั้งค่า API Key / Client ID ออกจากหน้าจอทั้งหมด ให้เหลือเพียงปุ่มเข้าสู่ระบบด้วย Google เพียงปุ่มเดียว (1-Click Sync)
  - ปรับปรุงโหมด Google OAuth Redirect เพื่อแก้ปัญหาหน้าจอสีขาวบนเบราว์เซอร์มือถือและ APK
- **v1.1.0:**
  - เพิ่มหน้าต่างจัดการลงปฏิทินสอบกลางภาค, ปลายภาค และการบ้าน (Calendar Export Modal)
  - เพิ่มระบบตรวจเช็คสถานะการมีอยู่จริงของกิจกรรมบน Google Calendar แบบสองทาง (Two-way Verification)
