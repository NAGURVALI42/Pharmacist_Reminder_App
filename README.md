# 💊 MediRemind: Pharmacist Reminder App

> **MediRemind** is a full-stack mobile healthcare application built with **Flutter**, **Node.js**, and **MySQL**. It is designed to help patients take their medicines on time while giving pharmacists and administrators complete, centralized control over patient management.

---

## 👥 User Roles

The system operates across four distinct permission levels to ensure smooth facility and patient management:

| Role | Responsibilities |
| :--- | :--- |
| **Super Admin** | Approves pharmacists, views system logs, and manages overall system settings. |
| **Pharmacist** | Manages patients, assigns medicines, sets up reminders, generates compliance reports, and handles prescriptions. |
| **Patient (Managed)** | Created by the pharmacist. Can view their medication schedule and mark medicines as taken or missed. |
| **Patient (Self-Managed)** | Registers independently. Manages their own medicines, reminders, and has access to the AI food advisor. |

---

## 📱 App Structure (33 Total Screens)

The application is divided into 5 core navigation flows:

* **Onboarding & Auth:** Login, Registration, Role Selection.
* **Admin Area:** Dashboard, Pharmacist Approvals, System Registry, Activity Logs, Settings, Profile.
* **Pharmacist Hub:** Dashboard, Patient List, Add/Import Patients, Medicine Manager, Reminder Manager, Compliance Reports, Prescriptions, Profile, Settings.
* **Patient (Managed):** Dashboard, Today's Medicines, Treatment Details, Prescription Viewer, History.
* **Patient (Self-Managed):** Dashboard, Multi-step Registration, Food AI, History, Reminder Popups.

---

## ✨ Key Technical Features

### 🔔 Smart Reminder Engine
* **Background Processing:** Checks scheduled medicines every 30 seconds in the background.
* **Proactive Alerts:** Triggers a popup 15 minutes before the scheduled intake time.
* **Actionable Prompts:** Patients can mark their dose as *Taken*, *Missed*, or *Snooze*.
* **Live Tracking:** Updates the patient's compliance score in real-time based on their actions.

### 🤖 AI Food Advisor (Google Gemini)
* **Contextual Advice:** Patients can type a condition (e.g., "Diabetes") or tap a quick-select chip.
* **AI Integration:** The backend queries Google Gemini AI to generate personalized dietary advice.
* **Clear Outputs:** Results are displayed in easy-to-read lists: ✅ *Recommended Foods* + 🚫 *Foods to Avoid*.

### 📊 Compliance Reports
* Pharmacists can view comprehensive reports detailing exactly which medicines were taken, missed, or skipped per day for every individual patient.

### 📥 Bulk Patient Import
* Pharmacists can upload an Excel file containing patient data.
* The backend parses the file using the `xlsx` library and securely registers all patients in a single batch process.

---

## 🌐 Backend Architecture (30+ API Endpoints)

The REST API is organized into modular, clean routes:

* 📁 `/auth` — Handles Super Admin/Pharmacist/Patient logins and self-registration.
* 📁 `/admin` — Manages pharmacist approvals, system logs, and global settings.
* 📁 `/pharmacist` — Handles patient CRUD operations, medicines, reminders, reports, and Excel imports.
* 📁 `/patient` — Fetches today's medicines, logs intake actions, interacts with the Food AI, and retrieves history.

---

## 🔐 Security & Integrity

* **Password Hashing:** Utilizing `Bcrypt` with 10 salt rounds.
* **Session Management:** Secured via `JWT` tokens with a 1-day strict expiration.
* **Access Control:** Accounts must achieve an `APPROVED` status before login functionality is unlocked.
* **Data Integrity:** Core operations (like user registration) utilize database transactions with automatic rollback upon failure.

---

## 🛠️ Tech Stack

| Layer | Technology |
| :--- | :--- |
| **Mobile App** | Flutter 3.x (Dart) |
| **Backend API** | Node.js + Express.js |
| **Database** | MySQL (with connection pooling) |
| **Authentication** | JWT + Bcrypt |
| **AI Integration** | Google GenAI (Gemini) |
| **Offline Storage** | Hive (NoSQL local DB) |
| **File Uploads** | Multer |
| **Excel Import** | XLSX library |
| **Notifications** | `flutter_local_notifications` |
