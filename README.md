# Pharmacist_Reminder_App
🧠 What Your Project Is
MediRemind is a full-stack mobile healthcare application built with Flutter + Node.js + MySQL. It helps patients take their medicines on time while giving pharmacists and admins complete control over patient management.

👥 The 4 User Roles
Role	What They Do
Super Admin	Approves pharmacists, views logs, manages system settings
Pharmacist	Manages patients, assigns medicines, sets reminders, generates compliance reports
Patient (Managed)	Created by pharmacist — views schedule, marks medicines taken/missed
Patient (Self-Managed)	Registers independently, manages own medicines + reminders + AI food advice
📱 Total Screens: 33
Your app has 33 screens across 5 categories:

Onboarding/Auth — Login, Registration, Role Selection
Admin — Dashboard, Pharmacist Approvals, System Registry, Activity Logs, Settings, Profile
Pharmacist — Dashboard, Patient List, Add/Import Patients, Medicine Manager, Reminder Manager, Compliance Reports, Prescriptions, Profile, Settings
Patient (Managed) — Dashboard, Today's Medicines, Treatment Details, Prescription Viewer, History
Patient (Self-Managed) — Dashboard, Multi-step Registration, Food AI, History, Reminder Popups
⚙️ Most Interesting Technical Features
🔔 Reminder Engine
Checks medicines every 30 seconds in the background
Triggers a popup 15 minutes before scheduled time
Patient can mark: Taken / Missed / Snooze
Updates compliance score in real time
🤖 AI Food Advisor (Google Gemini)
Patient types a condition like "Diabetes" or taps a quick chip
Backend calls Gemini AI and gets personalized food lists
Results show: ✅ Recommended Foods + 🚫 Foods to Avoid
📊 Compliance Reports
Pharmacist can view a full report: which medicines were taken, missed, or skipped per day for each patient
📥 Bulk Patient Import
Pharmacist uploads an Excel file → the backend parses it with xlsx and registers all patients at once
🌐 Backend: 30+ API Endpoints
Organized into clean route modules:

/auth → Login, Patient login, Self-registration
/admin → Pharmacist approvals, logs, settings
/pharmacist → Patient CRUD, medicines, reminders, reports, import
/patient → Today's medicines, intake logs, food AI, history
🔐 Security
Bcrypt password hashing (10 rounds)
JWT tokens (1-day expiry)
Accounts must be status APPROVED before login works
DB transactions used for registration (rollback on failure)
🛠️ Tech Stack Summary
Layer	Technology
Mobile App	Flutter 3.x (Dart)
Backend API	Node.js + Express.js
Database	MySQL (with connection pooling)
Auth	JWT + Bcrypt
AI Feature	Google GenAI (Gemini)
Offline Storage	Hive (NoSQL local DB)
File Uploads	Multer
Excel Import	XLSX library
Notifications	flutter_local_notifications
The full detailed brief is also saved as an artifact above with every screen, every API route, the database schema, architecture diagram, and more. You can copy it directly into your GitHub repository's 

README.md
 or use it for any project documentation or presentation.
