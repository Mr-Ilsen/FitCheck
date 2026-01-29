# FitCheck
## Real-Time Uniform Garment Detection System

FitCheck is a **real-time uniform detection and access control system** designed to automate uniform compliance checking at **National University – Fairview**. The system replaces manual inspection with a **computer vision–based solution** integrated with **RFID authentication, database logging, and a physical gate mechanism**.

This project was developed as an **Elective / Capstone Project** for the **Bachelor of Science in Computer Engineering** program.

---

## Project Overview

Manual uniform inspection at campus entry points often leads to:
- Long queues  
- Inconsistent enforcement  
- Human error and bias  
- Incomplete violation records  

**FitCheck** addresses these issues by using:
- Image-based uniform recognition  
- Automated student identification  
- Real-time violation logging  
- Email notifications  
- Physical access control  

The system ensures **fair, accurate, and transparent enforcement** of university uniform policies.

---

## Key Features

- 🎯 **Real-Time Uniform Detection**
  - Detects **three official NU uniform types**:
    - Traditional Uniform  
    - General Uniform with Logo  
    - PE Uniform  

- 🪪 **RFID-Based Student Identification**
  - Links detection results to student profiles  
  - Supports manual student number input when ID is unavailable  

- 🚪 **Automated Gate Control**
  - Single swing barrier gate opens only for compliant entries  

- 🗃 **Violation Logging**
  - Stores timestamps and image snapshots in a central database  

- 📧 **Automatic Email Notifications**
  - Sends warnings for 1st and 2nd violations  
  - Notifies student and Discipline Office on 3rd violation  

- 🛡 **Master Card Override**
  - Allows guards to log violations manually when needed  

---

## System Architecture (High-Level)

1. Student approaches the gate  
2. Camera captures uniform images  
3. Raspberry Pi processes images using a trained ML model  
4. Student taps RFID ID  
5. System validates:
   - Uniform compliance  
   - Student identity  
6. System actions:
   - **Correct uniform** → Gate opens, entry logged  
   - **Violation** → Logged + email sent  
7. On third violation:
   - ID is blocked  
   - Discipline Office is notified  

---

## Hardware Components

- Raspberry Pi  
- Dual high-definition cameras (front & side view)  
- RFID ID scanner  
- Single swing barrier gate (servo/actuator driven)  
- Control panel with keypad and Master Card access  
- Display screen for system messages  

---

## Software Components

- Python-based image processing pipeline  
- Machine learning model (CNN / lightweight detector)  
- Database for logs and student records  
- Email notification module  
- Admin dashboard for monitoring and reporting  

---

## Machine Learning Details

- Trained to classify **three uniform categories**
- Image preprocessing:
  - Resizing
  - Normalization
  - Data augmentation  
- Achieved performance:
  - ~95% precision  
  - ~98% recall  
  - ~93% mAP  
- Optimized for **Raspberry Pi deployment**

---

## Project Scope

- Detects **upper-body uniform garments only**
- Operates at **NU–Fairview campus gates**
- Records violations even without RFID (manual input)
- Enforces **3-strike uniform policy**

---

## Limitations

- Detection accuracy may be affected by:
  - Poor lighting conditions  
  - Student crowding / overlap  
  - Camera angle misalignment  

- Does **not** detect:
  - Shoes  
  - Socks  
  - Accessories  

- Requires stable power and network connectivity

---

## Testing Summary

- ✔ Uniform classification accuracy validated  
- ✔ Gate response tested with valid and invalid IDs  
- ✔ Database logging verified (timestamps + images)  
- ✔ Email notifications delivered reliably  
- ✔ Third-violation escalation confirmed  

---

## Future Improvements

- Support for **department-specific uniforms**
- Improved low-light detection
- Crowd-handling logic (one-student-at-a-time)
- Deeper integration with university information systems
- Expanded admin analytics and reporting

---

## Developers

- Arnoco, Khristina Bernadette M.  
- Castro, Kaxandra A.  
- Deguito, Keith Nestle S.  
- Narisma, Jaizel Zanch C.  

**Program:** BS Computer Engineering  
**Institution:** National University – Fairview  
**Adviser:** Engr. John Kenneth San Luis, CCpE  

---

## License

This project is intended for **academic and research purposes**.  
Usage, modification, or deployment outside this context requires permission from the authors and National University – Fairview.
