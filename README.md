<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&height=220&color=gradient&customColorList=0,2,2,5,30&text=Tabibak%20%7C%20%D8%B7%D8%A8%D9%8A%D8%A8%D9%83&fontSize=56&fontColor=ffffff&fontAlignY=38&desc=Smart%20Clinic%20Management%20Platform&descAlignY=60&descSize=20&animation=fadeIn" width="100%" alt="Tabibak" />

**A complete healthcare backend: appointments, real-time doctor–patient chat, digital prescriptions, medical records and AI-powered specialty recommendations.**

<p>
  <img src="https://img.shields.io/badge/.NET-8.0-512BD4?style=for-the-badge&logo=dotnet&logoColor=white" />
  <img src="https://img.shields.io/badge/C%23-12-68217A?style=for-the-badge&logo=csharp&logoColor=white" />
  <img src="https://img.shields.io/badge/EF_Core-8-512BD4?style=for-the-badge&logo=dotnet&logoColor=white" />
  <img src="https://img.shields.io/badge/SQL_Server-CC2927?style=for-the-badge&logo=microsoftsqlserver&logoColor=white" />
  <img src="https://img.shields.io/badge/SignalR-Real--Time-0078D7?style=for-the-badge&logo=dotnet&logoColor=white" />
  <img src="https://img.shields.io/badge/JWT-Auth-000000?style=for-the-badge&logo=jsonwebtokens&logoColor=white" />
  <img src="https://img.shields.io/badge/Swagger-OpenAPI-85EA2D?style=for-the-badge&logo=swagger&logoColor=black" />
</p>

<p>
  <a href="http://tabibakv1.runasp.net/swagger/index.html"><img src="https://img.shields.io/badge/🌐_Live_API-Swagger-2EA44F?style=for-the-badge" alt="Live API" /></a>
  <img src="https://img.shields.io/badge/Hosted_on-MonsterASP-FF6B35?style=for-the-badge" alt="Hosted on MonsterASP" />
  <img src="https://img.shields.io/badge/🎓_Graduation_Project-2026-6C5CE7?style=for-the-badge" alt="Graduation Project" />
</p>

</div>

---

## 📊 At a Glance

<div align="center">

| 🧱 Layers | 🌐 Controllers | 🔌 Endpoints | 🗃️ Entities | 📄 DTOs | ✅ Validators |
|:---:|:---:|:---:|:---:|:---:|:---:|
| **4** | **21** | **154+** | **26** | **78** | **13** |

| 💾 Migrations | 👥 Roles | 🔑 Permissions | 🛡️ Policies | 📡 SignalR Hub | ⏰ Background Jobs |
|:---:|:---:|:---:|:---:|:---:|:---:|
| **41** | **6** | **28** | **31** | **1** | **2** |

</div>

---

## 📑 Table of Contents

1. [Overview](#-overview)
2. [Key Features](#-key-features)
3. [Architecture](#-architecture)
4. [UML Diagrams](#-uml-diagrams)
5. [Sequence Diagrams](#-sequence-diagrams)
6. [API Reference](#-api-reference)
7. [Roles & Permissions](#-roles--permissions)
8. [Tech Stack](#-tech-stack)
9. [Getting Started](#-getting-started)
10. [Hosting & Deployment](#-hosting--deployment)
11. [Author](#-author)

---

## 📖 Overview

> **Tabibak (طبيبك)** means *"your doctor"* in Arabic.

| | |
|:--|:--|
| 🎯 **The problem** | Many clinics still rely on paper records and phone-call bookings, which leads to missed appointments, lost medical history and a poor patient experience. |
| 💡 **The solution** | One digital platform that connects **patients**, **doctors** and **clinic staff**: online booking, real-time chat and video consultations, digital prescriptions, lab results and complete medical records. |
| 🤖 **The smart part** | Patients describe their symptoms in plain words, and an **AI model** recommends the right medical specialty and matching doctors. |

This repository contains the **backend REST API**, built with ASP.NET Core 8 and a 4-layer Clean Architecture. It's the graduation project of the **Computer Science & Artificial Intelligence** program.

---

## ✨ Key Features

### ⭐ Highlights

| Feature | How it works |
|:--|:--|
| 🤖 **AI specialty matching** | Symptoms go to an external ML service (Hugging Face Space); the API returns the recommended specialty plus matching doctors |
| 💬 **Real-time chat** | REST + SignalR hub at `/hubs/chat` with **delivered** and **read** receipts, editing and deleting messages |
| 💊 **Digital prescriptions** | Itemized prescriptions from an **Egyptian medicine database** imported from Excel (ClosedXML) |
| 📍 **Nearby doctors** | Geo-search with **NetTopologySuite** (SQL Server spatial) to find doctors close to the patient |
| 🔒 **Security** | JWT access tokens + **refresh tokens**, **claims-based** permissions, OTP-based password reset and email verification |
| ⏰ **Smart reminders** | A background service emails patients before their appointments (MailKit + HTML templates) |
| 📊 **Dashboards** | Analytics for doctors (appointments, patients, ratings, earnings) and for admins (users, revenue, content) |

### 🧑‍🤒 Patient

- 🔍 **Find doctors**: search by specialization and name, or find **nearby** doctors sorted by distance
- 🤖 **AI recommendation**: describe symptoms → get a specialty suggestion
- 📅 **Appointments**: book, reschedule or cancel
- ⏰ **Email reminders** before upcoming appointments
- 📄 **Prescriptions**: view current and past prescriptions, including digital ones
- 🧪 **Lab tests & medical records** with downloadable file attachments
- 💬 **Chat** with your doctor in real time
- 💳 **Payment records** for consultations
- 📰 **Health content**: read doctors' advice posts and watch advice videos

### 👨‍⚕️ Doctor

- 🗓️ **Schedule management**: working days and hours, checked automatically when patients book
- 📊 **Dashboard**: today's appointments, recent patients, statistics, ratings and earnings
- 🏥 **Patient records**: medical history, diagnoses, lab tests and files
- 💊 **Prescriptions**: classic and digital prescriptions from the medicine catalog
- 📰 **Advice posts**: publish posts that patients can like, comment on and save
- 🎥 **Advice videos**: upload educational videos
- 💬 **Real-time chat** with patients
- ⭐ **Ratings & reviews** from patients

### 🛡️ Admin

- 📈 **Analytics**: registrations, appointments, revenue trend, top specializations
- 👥 **User management**: view, ban, activate, change role, delete
- ✅ **Doctor verification**: review professional card, medical license and national ID, then verify or reject
- 📅 **Appointment control**: force-cancel or force-complete
- 📰 **Content moderation**: publish/unpublish or delete posts and videos, remove ratings
- 💰 **Finance**: revenue summary, revenue by doctor, revenue trend
- 🔑 **Roles & permissions**: manage roles, role claims and user roles
- 📝 **Structured logging** with Serilog (console + SQL Server)

---

## 📐 Architecture

Tabibak follows a **4-layer Clean Architecture**. Each layer is its own project, and dependencies point **inward** toward the domain:

```mermaid
flowchart TD
    C([📱 Web / Mobile clients]) -->|HTTPS + JWT| API
    C <-->|WebSocket| HUB

    subgraph API["🌐 API_Layer (ClinicAPI)"]
        CT[22 Controllers]
        HUB[ChatHub · SignalR]
        MW[Middlewares · Error handling · Logging]
        BG[Background services · Reminders · AI keep-alive]
    end

    subgraph BL["⚙️ BusinessLayer"]
        SV[Services]
        VAL[FluentValidation validators]
        MAP[AutoMapper profile]
    end

    subgraph DAL["💾 DataAccessLayer"]
        CTX[ApplicationDbContext]
        UOW[Unit of Work + Generic Repository]
        SEED[Seeders]
    end

    subgraph DOM["🧱 DomainLayer"]
        M[Entities · DTOs · Interfaces · Enums · Constants]
    end

    API --> BL
    API --> DAL
    BL --> DAL
    API --> DOM
    BL --> DOM
    DAL --> DOM
    CTX --> DB[(SQL Server)]
    BG --> SMTP[[SMTP]]
    API --> AI[[AI service · Hugging Face]]
```

| Layer | Project | Contents |
|:--|:--|:--|
| 🧱 **Domain** | `DomainLayer` | Entities (`ApplicationUser`, `Doctor`, `Patient`, `Appointment`, …), 78 DTOs, service interfaces, enums, roles, claims and policy constants |
| 💾 **Data Access** | `DataAccessLayer` | `ApplicationDbContext`, Fluent API configurations, Generic Repository, Unit of Work, seeders, 41 migrations |
| ⚙️ **Business** | `BusinessLayer` | Service implementations, 13 FluentValidation validators, AutoMapper mapping |
| 🌐 **API** | `ClinicAPI` (`API_Layer`) | Controllers in 5 areas, SignalR `ChatHub`, middlewares, DI extensions, background services |

### 🖼️ System Architecture

<p align="center"><img src="Imagse/modern_architecture_diagram.png" alt="System architecture" width="90%" /></p>

<details>
<summary><b>Detailed architecture diagram</b></summary>

<p align="center"><img src="Imagse/01_system_architecture.png" alt="Detailed system architecture" width="90%" /></p>

</details>

### 📁 Project Structure

```
TabibaK/
├── API_Layer/                  # 🌐 Presentation (ClinicAPI.csproj)
│   ├── Controllers/
│   │   ├── Admin/              # Admin dashboard, roles, role claims, user roles
│   │   ├── Auth/               # Login, tokens, password reset, profile
│   │   ├── Doctor/             # Doctors, dashboard, advice posts/videos, AI, finance
│   │   ├── Patient/            # Patients, appointments, records, prescriptions, payments
│   │   └── Shared/             # Chat, files, medicines, lab tests
│   ├── Hubs/                   # ChatHub (SignalR)
│   ├── Middlewares/            # GlobalErrorHandling, LoggingAsyncMiddleware, SuperAdmin handler
│   ├── Extensions/             # DI setup and startup pipeline
│   ├── Services/               # Appointment reminders, AI keep-alive, medicine Excel seeder, …
│   └── Program.cs
│
├── BusinessLayer/              # ⚙️ Application logic
│   ├── Services/
│   ├── Validations/            # FluentValidation
│   └── Mapping/                # AutoMapper profile
│
├── DataAccessLayer/            # 💾 Persistence
│   ├── Persistence/            # DbContext + configurations
│   ├── Repositories/           # Generic repository
│   ├── UnitOfWork/
│   ├── Seeding/                # Permissions, admin user, test data
│   └── Migrations/
│
├── DomainLayer/                # 🧱 Core
│   ├── Models/  DTOs/  Interfaces/  Enums/  Constants/  Helpers/
│
└── Imagse/                     # Architecture, UML and sequence diagrams
```

---

## 🧩 UML Diagrams

<details open>
<summary><b>Class diagram</b></summary>

<p align="center"><img src="Imagse/UML_Class_Diagram.png" alt="UML class diagram" width="95%" /></p>

</details>

<details>
<summary><b>Use case diagram</b></summary>

<p align="center"><img src="Imagse/UML_UseCase_Diagram.png" alt="UML use case diagram" width="90%" /></p>

</details>

---

## 🔄 Sequence Diagrams

Click a flow to see how a request moves through the system.

<details>
<summary><b>🔐 Authentication & registration</b></summary>

<img src="Imagse/01_auth_registration.png" alt="Authentication and registration" width="100%" />
<img src="Imagse/03_authentication_flow.png" alt="Authentication flow" width="100%" />

</details>

<details>
<summary><b>📅 Appointment lifecycle</b></summary>

<img src="Imagse/04_appointment_service.png" alt="Appointment service" width="100%" />
<img src="Imagse/02_request_lifecycle.png" alt="Request lifecycle" width="100%" />

</details>

<details>
<summary><b>👨‍⚕️ Doctor management</b></summary>

<img src="Imagse/02_doctor_management.png" alt="Doctor management" width="100%" />

</details>

<details>
<summary><b>🧑‍🤒 Patient management</b></summary>

<img src="Imagse/03_patient_management.png" alt="Patient management" width="100%" />

</details>

<details>
<summary><b>💊 Prescriptions</b></summary>

<img src="Imagse/05_prescriptions.png" alt="Prescriptions" width="100%" />

</details>

<details>
<summary><b>🏥 Medical records & lab tests</b></summary>

<img src="Imagse/06_medical_records_testing.png" alt="Medical records and lab tests" width="100%" />

</details>

<details>
<summary><b>💬 Real-time chat (SignalR)</b></summary>

<img src="Imagse/05_signalr_chat.png" alt="SignalR chat" width="100%" />
<img src="Imagse/07_chat_signalr.png" alt="Chat with SignalR" width="100%" />

</details>

<details>
<summary><b>📞 WebRTC calls (design)</b></summary>

<img src="Imagse/15_webrtc_calls.png" alt="WebRTC calls" width="100%" />

</details>

<details>
<summary><b>🤖 AI specialty recommendation</b></summary>

<img src="Imagse/04_ai_recommendation.png" alt="AI recommendation" width="100%" />
<img src="Imagse/08_ai_integration.png" alt="AI integration" width="100%" />

</details>

<details>
<summary><b>💳 Payments & files</b></summary>

<img src="Imagse/09_payment_file_services.png" alt="Payment and file services" width="100%" />

</details>

<details>
<summary><b>⏰ Email & reminders</b></summary>

<img src="Imagse/06_reminder_service.png" alt="Reminder service" width="100%" />
<img src="Imagse/17_email_notification.png" alt="Email notifications" width="100%" />

</details>

<details>
<summary><b>📊 Doctor dashboard</b></summary>

<img src="Imagse/16_dashboard_service.png" alt="Doctor dashboard" width="100%" />

</details>

<details>
<summary><b>💾 Data access (Repository + Unit of Work)</b></summary>

<img src="Imagse/07_data_access_layer.png" alt="Data access layer" width="100%" />
<img src="Imagse/10_data_access_layer.png" alt="Data access layer details" width="100%" />

</details>

<details>
<summary><b>🔑 Authorization & security</b></summary>

<img src="Imagse/08_authorization_matrix.png" alt="Authorization matrix" width="100%" />
<img src="Imagse/14_security_optimization.png" alt="Security" width="100%" />

</details>

<details>
<summary><b>🌐 Middleware pipeline</b></summary>

<img src="Imagse/11_api_gateway_middleware.png" alt="Middleware pipeline" width="100%" />

</details>

<details>
<summary><b>🚀 Startup & initialization</b></summary>

<img src="Imagse/13_startup_initialization.png" alt="Startup and initialization" width="100%" />

</details>

---

## 🔌 API Reference

**154 endpoints** across **21 controllers**. All routes start with `/api`. The full interactive docs are on the **[live Swagger UI](http://tabibakv1.runasp.net/swagger/index.html)**.

**Access column:** `Public` = no login · `Authenticated` = any logged-in user · a role name (e.g. `Doctor`) = that role only · `CanView…` = a permission-based policy.

<details>
<summary><b>Auth</b>: Auth (9 endpoints)</summary>

#### Auth

| Method | Route | Access |
|:--|:--|:--|
| `POST` | `/api/Auth/register` | SuperAdmin |
| `POST` | `/api/Auth/login` | Public |
| `POST` | `/api/Auth/forgot-password/request` | Public |
| `POST` | `/api/Auth/forgot-password/verify` | Public |
| `POST` | `/api/Auth/refresh-token` | Public |
| `POST` | `/api/Auth/revoke-token` | Public |
| `GET` | `/api/Auth/profile` | Authenticated |
| `POST` | `/api/Auth/change-password/request-code` | Authenticated |
| `POST` | `/api/Auth/change-password` | Authenticated |

</details>

<details>
<summary><b>Patient</b>: Appointment, DigitalPrescription, MedicalRecord, Patient, Payment, Prescription (34 endpoints)</summary>

#### Appointment

| Method | Route | Access |
|:--|:--|:--|
| `POST` | `/api/Appointment` | CanCreateAppointment |
| `PUT` | `/api/Appointment/reschedule-appointment` | CanRescheduleAppointment |
| `DELETE` | `/api/Appointment/cancel-appointment/{appointmentId}` | CanCancelAppointment |
| `PUT` | `/api/Appointment/complete-appointment` | CanCompleteAppointment |
| `GET` | `/api/Appointment` | CanViewAppointments |
| `GET` | `/api/Appointment/{id}` | CanViewAppointments |
| `POST` | `/api/Appointment/rate` | CanViewAppointments |

#### DigitalPrescription

| Method | Route | Access |
|:--|:--|:--|
| `GET` | `/api/DigitalPrescription` | CanViewPrescriptions |
| `GET` | `/api/DigitalPrescription/{id}` | CanViewPrescriptions |
| `GET` | `/api/DigitalPrescription/medical-record/{medicalRecordId}` | CanViewPrescriptions |
| `GET` | `/api/DigitalPrescription/patient/{patientId}` | CanViewPrescriptions |
| `POST` | `/api/DigitalPrescription` | CanCreateDigitalPrescription |
| `PUT` | `/api/DigitalPrescription/{id}` | CanEditDigitalPrescription |
| `DELETE` | `/api/DigitalPrescription/{id}` | CanDeleteDigitalPrescription |

#### MedicalRecord

| Method | Route | Access |
|:--|:--|:--|
| `GET` | `/api/MedicalRecord` | CanViewMedicalRecords |
| `GET` | `/api/MedicalRecord/{id}` | CanViewMedicalRecords |
| `GET` | `/api/MedicalRecord/patient/{patientId}` | CanViewMedicalRecords |
| `DELETE` | `/api/MedicalRecord/{id}` | CanDeleteMedicalRecord |

#### Patient

| Method | Route | Access |
|:--|:--|:--|
| `GET` | `/api/Patient` | CanViewPatients |
| `POST` | `/api/Patient` | Public |
| `POST` | `/api/Patient/verify-email` | Public |
| `GET` | `/api/Patient/{id}` | Authenticated |
| `DELETE` | `/api/Patient/{patientId}` | CanDeletePatient |
| `PUT` | `/api/Patient` | Authenticated |

#### Payment

| Method | Route | Access |
|:--|:--|:--|
| `GET` | `/api/Payment` | CanViewPayments |
| `GET` | `/api/Payment/{id}` | CanViewPayments |
| `PUT` | `/api/Payment` | CanProcessPayment |

#### Prescription

| Method | Route | Access |
|:--|:--|:--|
| `POST` | `/api/Prescription` | CanCreatePrescription |
| `GET` | `/api/Prescription/medical-record/{medicalRecordId}` | CanViewPrescriptions |
| `GET` | `/api/Prescription/patient/{patientId}` | CanViewPrescriptions |
| `PUT` | `/api/Prescription` | CanEditPrescription |
| `GET` | `/api/Prescription` | CanViewPrescriptions |
| `GET` | `/api/Prescription/{id}` | CanViewPrescriptions |
| `DELETE` | `/api/Prescription/{id}` | CanDeletePrescription |

</details>

<details>
<summary><b>Doctor</b>: DashboardDoctor, DoctorAdvicePost, DoctorAdviceVideo, Doctor, DoctorFinancial, DoctorsAi (45 endpoints)</summary>

#### DashboardDoctor

| Method | Route | Access |
|:--|:--|:--|
| `GET` | `/api/DashboardDoctor/overview` | Authenticated |
| `GET` | `/api/DashboardDoctor/today-appointments` | Authenticated |
| `GET` | `/api/DashboardDoctor/next-appointment` | Authenticated |
| `GET` | `/api/DashboardDoctor/recent-patients` | Authenticated |
| `PUT` | `/api/DashboardDoctor/availability` | Authenticated |
| `GET` | `/api/DashboardDoctor/scheduled-appointments` | Authenticated |
| `GET` | `/api/DashboardDoctor/past-medical-records` | Authenticated |
| `GET` | `/api/DashboardDoctor/future-medical-records` | Authenticated |
| `PUT` | `/api/DashboardDoctor/price` | Authenticated |
| `PUT` | `/api/DashboardDoctor/schedule` | Authenticated |
| `GET` | `/api/DashboardDoctor/schedule` | Authenticated |
| `GET` | `/api/DashboardDoctor/appointments/not-completed` | Authenticated |
| `GET` | `/api/DashboardDoctor/appointments/completed` | Authenticated |
| `GET` | `/api/DashboardDoctor/medical-records/patient/{patientId}/completed` | Authenticated |
| `GET` | `/api/DashboardDoctor/medical-records/patient/{patientId}/not-completed` | Authenticated |
| `GET` | `/api/DashboardDoctor/today-earnings` | Authenticated |

#### DoctorAdvicePost

| Method | Route | Access |
|:--|:--|:--|
| `GET` | `/api/DoctorAdvicePost` | Public |
| `GET` | `/api/DoctorAdvicePost/my` | Doctor |
| `GET` | `/api/DoctorAdvicePost/{id:guid}` | Public |
| `POST` | `/api/DoctorAdvicePost` | Doctor |
| `DELETE` | `/api/DoctorAdvicePost/{id:guid}` | Doctor |
| `POST` | `/api/DoctorAdvicePost/{id:guid}/like` | CanViewDoctorAdviceVideos |
| `GET` | `/api/DoctorAdvicePost/{id:guid}/likes` | Public |
| `POST` | `/api/DoctorAdvicePost/{id:guid}/save/{userId}` | Authenticated |
| `GET` | `/api/DoctorAdvicePost/saved/{userId}` | Authenticated |
| `POST` | `/api/DoctorAdvicePost/{id:guid}/comments` | CanViewDoctorAdviceVideos |
| `GET` | `/api/DoctorAdvicePost/{id:guid}/comments` | Public |
| `PUT` | `/api/DoctorAdvicePost/comments/{commentId:long}` | Authenticated |
| `DELETE` | `/api/DoctorAdvicePost/comments/{commentId:long}` | Authenticated |

#### DoctorAdviceVideo

| Method | Route | Access |
|:--|:--|:--|
| `GET` | `/api/DoctorAdviceVideo` | Public |
| `GET` | `/api/DoctorAdviceVideo/my` | Doctor |
| `GET` | `/api/DoctorAdviceVideo/{id:guid}` | Public |
| `POST` | `/api/DoctorAdviceVideo` | Doctor |
| `PUT` | `/api/DoctorAdviceVideo/{id:guid}` | Doctor |
| `DELETE` | `/api/DoctorAdviceVideo/{id:guid}` | Doctor |

#### Doctor

| Method | Route | Access |
|:--|:--|:--|
| `POST` | `/api/Doctor` | Public |
| `POST` | `/api/Doctor/verify-email` | Public |
| `PUT` | `/api/Doctor` | Authenticated |
| `GET` | `/api/Doctor/{id}` | Authenticated |
| `GET` | `/api/Doctor` | Public |
| `DELETE` | `/api/Doctor/{id}` | CanDeleteDoctor |
| `GET` | `/api/Doctor/search` | Public |
| `GET` | `/api/Doctor/nearby` | Public |

#### DoctorFinancial

| Method | Route | Access |
|:--|:--|:--|
| `GET` | `/api/DoctorFinancial/report` | Authenticated |

#### DoctorsAi

| Method | Route | Access |
|:--|:--|:--|
| `POST` | `/api/doctors/ai/recommend-by-symptoms` | Public |

</details>

<details>
<summary><b>Shared</b>: Chat, File, Medicines, Testing (23 endpoints)</summary>

#### Chat

| Method | Route | Access |
|:--|:--|:--|
| `POST` | `/api/Chat/conversations` | Authenticated |
| `GET` | `/api/Chat/conversations` | Authenticated |
| `GET` | `/api/Chat/conversations/by-participants` | Authenticated |
| `GET` | `/api/Chat/conversations/{id:guid}` | Authenticated |
| `POST` | `/api/Chat/conversations/{id:guid}/messages` | Authenticated |
| `GET` | `/api/Chat/conversations/{id:guid}/messages` | Authenticated |
| `PATCH` | `/api/Chat/conversations/{id:guid}/messages/{messageId:long}` | Authenticated |
| `DELETE` | `/api/Chat/conversations/{id:guid}/messages/{messageId:long}` | Authenticated |
| `POST` | `/api/Chat/conversations/{id:guid}/messages/{messageId:long}/delivered` | Authenticated |
| `POST` | `/api/Chat/conversations/{id:guid}/messages/{messageId:long}/read` | Authenticated |

#### File

| Method | Route | Access |
|:--|:--|:--|
| `POST` | `/api/File/upload` | Authenticated |
| `POST` | `/api/File/upload-multiple` | Authenticated |
| `POST` | `/api/File/upload-image` | Authenticated |
| `DELETE` | `/api/File/delete` | Authenticated |
| `GET` | `/api/File/exists` | Authenticated |

#### Medicines

| Method | Route | Access |
|:--|:--|:--|
| `GET` | `/api/Medicines` | Public |

#### Testing

| Method | Route | Access |
|:--|:--|:--|
| `GET` | `/api/Testing` | CanViewMedicalRecords |
| `GET` | `/api/Testing/{id}` | CanViewMedicalRecords |
| `GET` | `/api/Testing/medical-record/{medicalRecordId}` | CanViewMedicalRecords |
| `GET` | `/api/Testing/patient/{patientId}` | CanViewMedicalRecords |
| `POST` | `/api/Testing` | CanCreateMedicalRecord |
| `PUT` | `/api/Testing` | CanEditMedicalRecord |
| `DELETE` | `/api/Testing/{id}` | CanDeleteMedicalRecord |

</details>

<details>
<summary><b>Admin</b>: AdminDashboard, RoleClaim, Role, UserRole (43 endpoints)</summary>

#### AdminDashboard

| Method | Route | Access |
|:--|:--|:--|
| `GET` | `/api/AdminDashboard/overview` | SuperAdmin |
| `GET` | `/api/AdminDashboard/analytics/registrations` | SuperAdmin |
| `GET` | `/api/AdminDashboard/analytics/appointments` | SuperAdmin |
| `GET` | `/api/AdminDashboard/analytics/revenue` | SuperAdmin |
| `GET` | `/api/AdminDashboard/analytics/top-specializations` | SuperAdmin |
| `GET` | `/api/AdminDashboard/users` | SuperAdmin |
| `GET` | `/api/AdminDashboard/users/{id}` | SuperAdmin |
| `POST` | `/api/AdminDashboard/users/{id}/ban` | SuperAdmin |
| `POST` | `/api/AdminDashboard/users/{id}/activate` | SuperAdmin |
| `PUT` | `/api/AdminDashboard/users/{id}/role` | SuperAdmin |
| `DELETE` | `/api/AdminDashboard/users/{id}` | SuperAdmin |
| `GET` | `/api/AdminDashboard/doctors` | SuperAdmin |
| `POST` | `/api/AdminDashboard/doctors/{id}/verify` | SuperAdmin |
| `POST` | `/api/AdminDashboard/doctors/{id}/reject` | SuperAdmin |
| `PUT` | `/api/AdminDashboard/doctors/{id}/force-price` | SuperAdmin |
| `GET` | `/api/AdminDashboard/patients` | SuperAdmin |
| `GET` | `/api/AdminDashboard/appointments` | SuperAdmin |
| `PUT` | `/api/AdminDashboard/appointments/{id}/force-cancel` | SuperAdmin |
| `PUT` | `/api/AdminDashboard/appointments/{id}/force-complete` | SuperAdmin |
| `GET` | `/api/AdminDashboard/content/posts` | SuperAdmin |
| `DELETE` | `/api/AdminDashboard/content/posts/{id}` | SuperAdmin |
| `PUT` | `/api/AdminDashboard/content/posts/{id}/toggle-publish` | SuperAdmin |
| `GET` | `/api/AdminDashboard/content/videos` | SuperAdmin |
| `DELETE` | `/api/AdminDashboard/content/videos/{id}` | SuperAdmin |
| `PUT` | `/api/AdminDashboard/content/videos/{id}/toggle-publish` | SuperAdmin |
| `GET` | `/api/AdminDashboard/finance/summary` | SuperAdmin |
| `GET` | `/api/AdminDashboard/finance/revenue-by-doctor` | SuperAdmin |
| `GET` | `/api/AdminDashboard/finance/revenue-trend` | SuperAdmin |
| `GET` | `/api/AdminDashboard/system/recent-activity` | SuperAdmin |
| `GET` | `/api/AdminDashboard/system/ratings` | SuperAdmin |
| `DELETE` | `/api/AdminDashboard/system/ratings/{id}` | SuperAdmin |

#### RoleClaim

| Method | Route | Access |
|:--|:--|:--|
| `POST` | `/api/RoleClaim/CreateRoleClaim` | SuperAdmin |
| `PUT` | `/api/RoleClaim/UpdateRoleClaim` | SuperAdmin |
| `DELETE` | `/api/RoleClaim/DeleteRoleClaim` | SuperAdmin |
| `GET` | `/api/RoleClaim/GetAllRoleClaims` | SuperAdmin |
| `GET` | `/api/RoleClaim/GetClaimsByRoleId/{roleId}` | SuperAdmin |

#### Role

| Method | Route | Access |
|:--|:--|:--|
| `POST` | `/api/Role/add-role` | SuperAdmin |
| `PUT` | `/api/Role/update-role` | SuperAdmin |
| `GET` | `/api/Role/{id}` | SuperAdmin |
| `DELETE` | `/api/Role/{id}` | SuperAdmin |
| `GET` | `/api/Role` | SuperAdmin |

#### UserRole

| Method | Route | Access |
|:--|:--|:--|
| `POST` | `/api/UserRole/AddUserToRole` | SuperAdmin |
| `DELETE` | `/api/UserRole/RemoveUserFromRole` | SuperAdmin |

</details>

### 📡 Real-time hub

| Hub | URL | Used for |
|:--|:--|:--|
| `ChatHub` | `/hubs/chat` | Join a conversation, receive new messages, delivered and read receipts |

---

## 👥 Roles & Permissions

Tabibak uses **claims-based authorization**: each role gets a set of permission claims, and endpoints are protected by **31 policies** built on top of them.

| Role | Scope |
|:--|:--|
| 🔴 **SuperAdmin** | Full system access, including roles and permissions management |
| 🟠 **ClinicManager** | Clinic operations: patients, doctors, appointments, prescriptions, payments, videos |
| 🟡 **Receptionist** | Front desk: patients, appointments, payments |
| 🟢 **MedicalAdmin** | Medical data: records and prescriptions |
| 🔵 **Doctor** | Own practice: appointments, patients' records, prescriptions, content |
| 🟣 **Patient** | Own data: appointments, records, prescriptions, payments |

<details>
<summary><b>All 28 permissions</b></summary>

| Area | Permissions |
|:--|:--|
| 🧑‍🤒 Patients | `ViewPatients` · `AddPatient` · `EditPatient` · `DeletePatient` |
| 👨‍⚕️ Doctors | `ViewDoctors` · `AddDoctor` · `EditDoctor` · `DeleteDoctor` |
| 📅 Appointments | `ViewAppointments` · `CreateAppointment` · `EditAppointment` · `CancelAppointment` · `RescheduleAppointment` · `CompleteAppointment` |
| 🏥 Medical records | `ViewMedicalRecords` · `CreateMedicalRecord` · `EditMedicalRecord` · `DeleteMedicalRecord` |
| 💊 Prescriptions | `ViewPrescriptions` · `CreatePrescription` · `EditPrescription` · `DeletePrescription` |
| 💳 Payments | `ViewPayments` · `ProcessPayment` |
| 🎥 Advice videos | `ViewDoctorAdviceVideos` · `CreateDoctorAdviceVideo` · `EditDoctorAdviceVideo` · `DeleteDoctorAdviceVideo` |

</details>

---

## 🧰 Tech Stack

| Area | Technologies |
|:--|:--|
| **Framework** | .NET 8, ASP.NET Core Web API, C# 12 |
| **Database** | SQL Server, Entity Framework Core 8 (Code-First), NetTopologySuite (spatial) |
| **Auth** | ASP.NET Core Identity, JWT Bearer, refresh tokens, claims-based policies |
| **Real-time** | SignalR (chat and message receipts) |
| **Validation & mapping** | FluentValidation, AutoMapper |
| **Email** | MailKit + HTML templates |
| **Files & data** | ClosedXML (Excel medicine import), file uploads |
| **Logging** | Serilog (Console + SQL Server sinks, async) |
| **Docs** | Swagger / Swashbuckle with annotations and FluentValidation rules |
| **Config** | DotNetEnv (`.env` file) |
| **AI** | External ML model on Hugging Face Spaces, called over HTTP |

---

## 🚀 Getting Started

### Prerequisites

- [.NET 8 SDK](https://dotnet.microsoft.com/download/dotnet/8.0)
- SQL Server (LocalDB, Express or Developer)
- An SMTP account for emails (e.g. a Gmail app password)

### 1. Clone

```bash
git clone https://github.com/ahmedramzyelsheikh/TabibaK.git
cd TabibaK
```

### 2. Configure

Settings live in `API_Layer/appsettings.json`. Keep secrets out of it: create a **`.env`** file in the repository root (next to this README). It's loaded on startup and overrides `appsettings.json`, using `Section__Key` names:

```env
ConnectionStrings__default=Server=.;Database=Tabibak;Trusted_Connection=True;TrustServerCertificate=True;
Jwt__Key=<a long random secret>
Email__SmtpUser=<your email>
Email__SmtpPassword=<your SMTP / app password>
```

| Section | What it controls |
|:--|:--|
| `ConnectionStrings:default` | SQL Server database |
| `Jwt` | Signing key, issuer, audience, token lifetimes |
| `Email` | SMTP host, port, credentials and sender |
| `AiSettings` | Base URL and path of the AI specialty model |
| `WebRtc` | STUN / TURN server settings (prepared for calls) |
| `MedicinesExcel:Path` | Location of the medicines Excel file (default: `wwwroot/data/medicines.xlsx`) |

### 3. Run

```bash
dotnet run --project API_Layer
```

On startup the API automatically:

1. applies all **EF Core migrations**
2. seeds **roles and permissions**
3. creates the **admin account**
4. seeds **test data** for the doctor dashboard
5. imports the **medicine database** from Excel, if the file exists

Then open **Swagger** at `https://localhost:<port>/swagger`.

> 💡 The medicines Excel file isn't included in the repository. Put it at `API_Layer/wwwroot/data/medicines.xlsx` (or set `MedicinesExcel:Path`) to fill the medicine catalog used by digital prescriptions.

---

## 🌍 Hosting & Deployment

The API is deployed on **[MonsterASP](https://www.monsterasp.net/)**:

| | |
|:--|:--|
| 🌐 **Live API** | [tabibakv1.runasp.net/swagger](http://tabibakv1.runasp.net/swagger/index.html) |
| 🗄️ **Database** | Hosted SQL Server; migrations are applied on startup |
| 📁 **Files** | Uploaded images, documents and lab results are served by the API |
| 📡 **Real-time** | WebSockets enabled for SignalR |
| 🤖 **AI model** | Runs separately on Hugging Face Spaces |

<details>
<summary><b>Deployment diagrams</b></summary>

<img src="Imagse/09_deployment.png" alt="Deployment" width="100%" />
<img src="Imagse/12_deployment.png" alt="Deployment details" width="100%" />

</details>

---

## 👨‍💻 Author

<div align="center">

**Ahmed Ramzy**

Backend Developer · Computer Science & AI graduate

[![GitHub](https://img.shields.io/badge/GitHub-ahmedramzyelsheikh-181717?style=for-the-badge&logo=github)](https://github.com/ahmedramzyelsheikh)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-ahmedramzy01-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/ahmedramzy01)
[![Email](https://img.shields.io/badge/Email-ahmed.ramzy.elsheikh-EA4335?style=for-the-badge&logo=gmail&logoColor=white)](mailto:ahmed.ramzy.elsheikh@gmail.com)

⭐ If you find this project useful, give it a star!

<img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=0,2,2,5,30&height=110&section=footer" width="100%" />

</div>
