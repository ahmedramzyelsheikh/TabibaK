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
| 💬 **Chat** | Conversations over REST with editing and deleting; **delivered** and **read** receipts pushed live through SignalR (`/hubs/chat`) |
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
- 💬 **Chat** with your doctor, with delivered and read receipts
- 💳 **Payment records** for consultations
- 📰 **Health content**: read doctors' advice posts and watch advice videos

### 👨‍⚕️ Doctor

- 🗓️ **Schedule management**: working days, hours and slot length; bookings outside them, or within 20 minutes of another appointment, are rejected
- 📊 **Dashboard**: today's appointments, recent patients, statistics, ratings and earnings
- 🏥 **Patient records**: medical history, diagnoses, lab tests and files
- 💊 **Prescriptions**: classic and digital prescriptions from the medicine catalog
- 📰 **Advice posts**: publish posts that patients can like, comment on and save
- 🎥 **Advice videos**: upload educational videos
- 💬 **Chat** with patients
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

### 🗂️ Class Diagram

The domain has **25 entities** in five areas. The map shows how they connect; open an area below for its classes, fields and multiplicities.

```mermaid
flowchart TB
    subgraph USERS["👥 Users & auth"]
        AU["ApplicationUser"]
        DOC["Doctor"]
        PAT["Patient"]
        RT["RefreshToken"]
        SCH["DoctorSchedule"]
        ERN["DoctorEarning"]
        AU -->|"0..1"| DOC
        AU -->|"0..1"| PAT
        AU -->|"0..*"| RT
        DOC -->|"0..*"| SCH
        DOC -->|"0..*"| ERN
    end

    subgraph APPT["📅 Appointments"]
        AP["Appointment"]
        PAY["Payment"]
        RAT["DoctorRating"]
        AP -->|"0..1"| PAY
        AP -->|"0..1"| RAT
    end

    subgraph CLIN["🏥 Clinical"]
        MR["MedicalRecord"]
        RX["Prescription"]
        DRX["DigitalPrescription"]
        DRXI["DigitalPrescriptionItem"]
        MED["Medicine"]
        LAB["Testing (lab result)"]
        MR -->|"0..*"| RX
        MR -->|"0..*"| DRX
        MR -->|"0..*"| LAB
        DRX -->|"0..*"| DRXI
        DRXI -.->|"picked from"| MED
    end

    subgraph CONT["📰 Content"]
        POST["DoctorAdvicePost"]
        VID["DoctorAdviceVideo"]
        LIKE["AdviceLike"]
        COM["AdviceComment"]
        SAVE["SavedPost"]
        POST -->|"0..*"| LIKE
        POST -->|"0..*"| COM
        POST -->|"0..*"| SAVE
    end

    subgraph CHAT["💬 Chat"]
        CONV["Conversation"]
        MSG["Message"]
        MS["MessageStatus"]
        CALL["Call"]
        CONV -->|"0..*"| MSG
        MSG -->|"0..* per recipient"| MS
        CONV -->|"0..*"| CALL
    end

    PAT -->|"books 0..*"| AP
    DOC -->|"attends 0..*"| AP
    AP -->|"0..1"| MR
    PAT -->|"owns 0..1"| MR
    DOC -->|"writes 0..*"| MR
    DOC -->|"publishes"| CONT
    USERS -->|"patient ↔ doctor"| CHAT

    classDef user fill:#E3F2FD,stroke:#1E88E5,color:#0D47A1
    classDef appt fill:#FFF3E0,stroke:#FB8C00,color:#E65100
    classDef clin fill:#E8F5E9,stroke:#43A047,color:#1B5E20
    classDef cont fill:#F3E5F5,stroke:#8E24AA,color:#4A148C
    classDef chat fill:#E0F7FA,stroke:#00ACC1,color:#006064
    class AU,DOC,PAT,RT,SCH,ERN user
    class AP,PAY,RAT appt
    class MR,RX,DRX,DRXI,MED,LAB clin
    class POST,VID,LIKE,COM,SAVE cont
    class CONV,MSG,MS,CALL chat
```

<details>
<summary><b>👥 Users & authentication</b></summary>

```mermaid
classDiagram
    direction LR
    class ApplicationUser {
        <<IdentityUser>>
        +string Id
        +string FullName
        +string Email
        +string Gender
        +DateTime DateOfBirth
        +DateTime DateOfRegistration
        +Point Location
        +string ProfileImageUrl
    }
    class RefreshToken {
        +int Id
        +string Token
        +DateTime CreatedOn
        +DateTime ExpiresOn
        +DateTime RevokedOn
    }
    class Doctor {
        +string Id
        +string Specialization
        +string IdNo
        +string IdImageFrontUrl
        +string IdImageBackUrl
        +decimal Price
        +bool IsAvailable
        +decimal Rating
        +int RatingCount
        +string RejectionReason
    }
    class Patient {
        +string Id
    }
    class DoctorSchedule {
        +int Id
        +DayOfWeek DayOfWeek
        +TimeSpan StartTime
        +TimeSpan EndTime
        +int SlotDurationMinutes
        +bool IsActive
    }
    class DoctorEarning {
        +int Id
        +DateTime Date
        +decimal DailyEarnings
        +int AppointmentCount
    }
    ApplicationUser "1" -- "0..1" Doctor : shared key
    ApplicationUser "1" -- "0..1" Patient : shared key
    ApplicationUser "1" --> "*" RefreshToken
    Doctor "1" --> "*" DoctorSchedule
    Doctor "1" --> "*" DoctorEarning
```

</details>

<details>
<summary><b>📅 Appointments, payments & ratings</b></summary>

```mermaid
classDiagram
    direction LR
    class Appointment {
        +Guid AppointmentID
        +DateOnly AppointmentDate
        +TimeSpan AppointmentTime
        +AppointmentStatus AppointmentStatus
        +string AdditionalNotes
        +DateTimeOffset ReminderAt
        +bool ReminderSent
    }
    class AppointmentStatus {
        <<enumeration>>
        Pending
        Rescheduled
        Canceled
        Completed
    }
    class Payment {
        +int PaymentID
        +DateTime PaymentDate
        +float AmountPaid
        +string AdditionalNotes
    }
    class DoctorRating {
        +int Id
        +byte Rating
        +string Comment
        +DateTime CreatedAt
    }
    Patient "1" --> "*" Appointment : books
    Doctor "1" --> "*" Appointment : attends
    Appointment ..> AppointmentStatus
    Appointment "1" --> "0..1" Payment
    Appointment "1" --> "0..1" DoctorRating
    Doctor "1" --> "*" DoctorRating
    Patient "1" --> "*" DoctorRating : gives
```

</details>

<details>
<summary><b>🏥 Clinical: records, prescriptions & lab tests</b></summary>

```mermaid
classDiagram
    direction LR
    class MedicalRecord {
        +Guid MedicalRecordId
    }
    class Prescription {
        +Guid PrescriptionId
        +string Title
        +string FilePath
        +string FileType
        +PrescriptionStatus Status
    }
    class PrescriptionStatus {
        <<enumeration>>
        StillUnderDoctor
        Finished
    }
    class DigitalPrescription {
        +Guid DigitalPrescriptionId
        +DateTime CreatedAt
    }
    class DigitalPrescriptionItem {
        +Guid DigitalPrescriptionItemId
        +string MedicineName
        +int PerDay
        +string Spotlights
    }
    class Testing {
        +Guid TestingId
        +string Title
        +DateTime DateExam
        +string FilePath
        +string FileType
    }
    class Medicine {
        +int Id
        +string Name
        +string ArabicName
        +string ActiveIngredient
        +string Company
        +string Price
    }
    Patient "1" --> "0..1" MedicalRecord : owns
    Doctor "1" --> "*" MedicalRecord : writes
    Appointment "0..1" --> "0..1" MedicalRecord
    MedicalRecord "1" *-- "*" Prescription : file prescriptions
    MedicalRecord "1" *-- "*" DigitalPrescription
    MedicalRecord "1" *-- "*" Testing : lab results
    DigitalPrescription "1" *-- "*" DigitalPrescriptionItem
    DigitalPrescriptionItem ..> Medicine : picked from catalog
    Prescription ..> PrescriptionStatus
```

</details>

<details>
<summary><b>📰 Health content: posts & videos</b></summary>

```mermaid
classDiagram
    direction LR
    class DoctorAdvicePost {
        +Guid Id
        +string Content
        +string ImageUrl
        +DateTime CreatedAt
        +bool IsPublished
    }
    class DoctorAdviceVideo {
        +Guid Id
        +string Title
        +string Description
        +string VideoUrl
        +DateTime CreatedAt
        +bool IsPublished
    }
    class AdviceLike {
        +int Id
        +DateTime CreatedAt
    }
    class AdviceComment {
        +long Id
        +string Content
        +DateTime CreatedAt
        +DateTime EditedAt
        +bool IsDeleted
    }
    class SavedPost {
        +Guid Id
        +DateTime SavedAt
    }
    Doctor "1" --> "*" DoctorAdvicePost : publishes
    Doctor "1" --> "*" DoctorAdviceVideo : uploads
    DoctorAdvicePost "1" *-- "*" AdviceLike
    DoctorAdvicePost "1" *-- "*" AdviceComment
    DoctorAdvicePost "1" <-- "*" SavedPost
    ApplicationUser "1" --> "*" AdviceLike
    ApplicationUser "1" --> "*" AdviceComment
    ApplicationUser "1" --> "*" SavedPost
```

</details>

<details>
<summary><b>💬 Chat & logs</b></summary>

```mermaid
classDiagram
    direction LR
    class Conversation {
        +Guid Id
        +DateTime CreatedAtUtc
        +DateTime UpdatedAtUtc
    }
    class Message {
        +long Id
        +string Content
        +DateTime CreatedAtUtc
        +DateTime EditedAtUtc
        +bool IsDeleted
    }
    class MessageStatus {
        +MessageDeliveryStatus Status
        +DateTime UpdatedAtUtc
    }
    class MessageDeliveryStatus {
        <<enumeration>>
        Sent
        Delivered
        Read
    }
    class Call {
        +Guid Id
        +string CallerId
        +string CalleeId
        +DateTime StartedAtUtc
        +DateTime EndedAtUtc
    }
    class ChatAuditLog {
        +long Id
        +string ActorId
        +string Action
        +long MessageId
        +string Metadata
        +DateTime CreatedAtUtc
    }
    class ApiAuditLog {
        +Guid Id
        +DateTime Timestamp
        +string UserId
        +string Method
        +string Endpoint
        +int StatusCode
        +long DurationMs
        +string IpAddress
    }
    Patient "1" --> "*" Conversation
    Doctor "1" --> "*" Conversation
    Conversation "1" *-- "*" Message
    ApplicationUser "1" --> "*" Message : sends
    Message "1" *-- "*" MessageStatus : one per recipient
    MessageStatus ..> MessageDeliveryStatus
    Conversation "1" --> "*" Call
    Conversation "1" ..> "*" ChatAuditLog : logged in
```

</details>

### 🎭 Use Case Diagram

Who can do what in the system, based on the API endpoints:

```mermaid
flowchart LR
    P(("🧑<br/>Patient"))

    subgraph SYS["🩺 Tabibak"]
        direction TB
        subgraph ACC["Account (everyone)"]
            U1(["Register & verify email"])
            U2(["Log in / refresh token"])
            U3(["Reset or change password"])
            U4(["View profile"])
            U10(["Chat in real time"])
        end
        subgraph CARE["Patient care"]
            U5(["Search & find nearby doctors"])
            U6(["Get AI specialty recommendation"])
            U7(["Book / reschedule / cancel appointment"])
            U8(["Rate doctor"])
            U9(["View prescriptions & lab results"])
            U22(["Read advice posts & videos"])
        end
        subgraph PRACTICE["Doctor practice"]
            U11(["Manage schedule & price"])
            U12(["View dashboard & earnings"])
            U13(["View patients' medical records"])
            U23(["Complete appointment"])
            U14(["Issue digital prescription"])
            U15(["Upload lab results & files"])
            U16(["Publish advice posts & videos"])
        end
        subgraph ADMIN["Administration"]
            U17(["Verify or reject doctors"])
            U18(["Manage users, roles & permissions"])
            U19(["Moderate content & ratings"])
            U20(["View analytics & revenue"])
            U21(["Force-cancel / complete appointments"])
        end
    end

    D(("🩺<br/>Doctor"))
    A(("🛡️<br/>Admin<br/><small>SuperAdmin · ClinicManager<br/>MedicalAdmin · Receptionist</small>"))
    AI[["🤖 AI model<br/>(Hugging Face)"]]
    MAIL[["📧 Email<br/>(SMTP)"]]

    P --- U1 & U2 & U3 & U4 & U10
    P --- U5 & U6 & U7 & U8 & U9 & U22
    U1 & U2 & U3 & U4 & U10 --- D
    U11 & U12 & U13 & U23 & U14 & U15 & U16 --- D
    U2 & U17 & U18 & U19 & U20 & U21 --- A

    U6 -.->|calls| AI
    U1 -.->|code| MAIL
    U3 -.->|OTP| MAIL
    U7 -.->|reminder| MAIL

    classDef actor fill:#FFF8E1,stroke:#F9A825,color:#5D4037
    classDef ext fill:#ECEFF1,stroke:#607D8B,color:#263238
    class P,D,A actor
    class AI,MAIL ext
```

---

## 🔄 Sequence Diagrams

Each diagram follows the real code path. Click a flow to open it.

<details>
<summary><b>🔐 Registration with email verification</b></summary>

Used by both patients (`POST /api/Patient`) and doctors (`POST /api/Doctor`). The account is only created after the emailed code is confirmed.

```mermaid
sequenceDiagram
    autonumber
    actor U as Patient / Doctor
    participant C as PatientController
    participant F as FileService
    participant A as AuthService
    participant Cache as MemoryCache
    participant M as Email (SMTP)
    participant S as PatientService
    participant ID as UserManager
    participant DB as SQL Server

    U->>C: POST /api/Patient (form + profile image)
    C->>F: Validate image (type, max 5 MB) and save
    F-->>C: image URL
    C->>ID: Is the email already used?
    ID-->>C: no
    C->>A: CachePendingRegistrationAsync(email, data)
    A->>Cache: store 6-digit code + registration data (60 s)
    A->>M: send verification code
    C-->>U: 200 "check your email"

    U->>C: POST /api/Patient/verify-email (email, code)
    C->>A: VerifyOtpAndGetPendingAsync
    A->>Cache: compare code, read data, then remove both
    alt wrong or expired code
        A-->>C: invalid
        C-->>U: 400 Invalid or expired code
    else code OK
        C->>S: Add(patient, password)
        S->>ID: CreateAsync(user) + AddToRole(Patient)
        S->>DB: insert Patient + empty MedicalRecord
        S--)M: welcome email (fire and forget)
        C-->>U: 201 Created
    end
```

</details>

<details>
<summary><b>🔑 Login, refresh token & password reset</b></summary>

```mermaid
sequenceDiagram
    autonumber
    actor U as User
    participant C as AuthController
    participant A as AuthService
    participant ID as UserManager
    participant UoW as UnitOfWork
    participant Cache as MemoryCache
    participant M as Email (SMTP)

    U->>C: POST /api/Auth/login (email, password)
    C->>A: Login
    A->>ID: find user + CheckPasswordAsync
    alt wrong credentials
        A-->>C: not authenticated
        C-->>U: 401
    else valid
        A->>A: build JWT (roles + permission claims)
        A->>UoW: reuse active refresh token or create a new one
        A-->>C: access token + refresh token
        C-->>U: 200
    end

    Note over U,C: When the access token expires
    U->>C: POST /api/Auth/refresh-token
    C->>A: RefreshToken(token)
    A->>UoW: revoke old token, add new token
    A-->>U: new access + refresh token

    Note over U,C: Forgot password
    U->>C: POST /forgot-password/request (email)
    C->>A: create 6-digit code
    A->>Cache: store code (5 min)
    A->>M: send code
    U->>C: POST /forgot-password/verify (email, code, new password)
    C->>A: check code
    A->>ID: RemovePassword + AddPassword (new password)
    A-->>U: password changed
```

</details>

<details>
<summary><b>📅 Booking an appointment</b></summary>

```mermaid
sequenceDiagram
    autonumber
    actor P as Patient
    participant C as AppointmentController
    participant S as AppointmentService
    participant Cache as MemoryCache
    participant DB as SQL Server
    participant M as Email (SMTP)

    P->>C: POST /api/Appointment
    Note right of C: policy CanCreateAppointment
    C->>S: Add(appointment)
    S->>S: validate input
    S->>DB: doctor and patient exist?
    S->>Cache: doctor schedule (cached 30 min)
    opt not in cache
        S->>DB: load active DoctorSchedules
    end
    alt outside the doctor's working hours
        S-->>P: 400 Doctor is not available at this day/time
    else another appointment within 20 minutes
        S-->>P: 400 Choose a time at least 20 minutes apart
    else slot is free
        S->>S: set ReminderAt (before the appointment)
        S->>DB: insert Appointment (+ MedicalRecord)
        opt doctor has a price
            S->>DB: insert Payment and link it
        end
        S--)M: confirmation to patient and doctor
        S-->>C: appointment
        C-->>P: 201 Created
    end
```

</details>

<details>
<summary><b>✅ Completing an appointment</b></summary>

```mermaid
sequenceDiagram
    autonumber
    actor D as Doctor
    participant C as AppointmentController
    participant S as AppointmentService
    participant UoW as UnitOfWork
    participant DB as SQL Server
    participant Dash as DashboardDoctorService

    D->>C: PUT /api/Appointment/complete-appointment
    Note right of C: policy CanCompleteAppointment
    C->>S: Complete(dto)
    S->>S: validate request
    S->>UoW: BEGIN TRANSACTION
    opt appointment has a medical record
        S->>UoW: add Prescription
    end
    S->>UoW: add Payment
    S->>UoW: status = Completed, link payment
    S->>UoW: SaveChanges + COMMIT
    alt any step fails
        S->>UoW: ROLLBACK
        S-->>D: 500 Failed to complete the appointment
    else success
        S->>Dash: UpsertDailyEarning(doctor, amount)
        Dash->>DB: update DoctorEarning for today
        S-->>D: 200
    end
```

</details>

<details>
<summary><b>⭐ Rating a doctor</b></summary>

```mermaid
sequenceDiagram
    autonumber
    actor P as Patient
    participant C as AppointmentController
    participant S as AppointmentService
    participant DB as SQL Server

    P->>C: POST /api/Appointment/rate (appointmentId, 1-5, comment)
    C->>S: SubmitRating(dto, patientId)
    S->>DB: load appointment
    alt not completed / not your appointment / already rated
        S-->>P: 400 with the reason
    else allowed
        S->>DB: insert DoctorRating
        S->>DB: recalculate doctor Rating (average) + RatingCount
        S-->>P: 200
    end
```

</details>

<details>
<summary><b>💊 Issuing a digital prescription</b></summary>

```mermaid
sequenceDiagram
    autonumber
    actor D as Doctor
    participant C as DigitalPrescriptionController
    participant S as DigitalPrescriptionService
    participant DB as SQL Server

    D->>C: GET /api/Medicines?name=... (pick medicines)
    C-->>D: matching medicines (Egyptian drug database)
    D->>C: POST /api/DigitalPrescription (medicalRecordId, items)
    Note right of C: policy CanCreateDigitalPrescription
    C->>S: Create(dto, doctorId)
    S->>DB: medical record exists?
    S->>DB: is it linked to one of this doctor's appointments?
    alt not your patient's record
        S-->>D: 403 Forbidden
    else allowed
        S->>DB: insert DigitalPrescription + items (medicine, per day, notes)
        S-->>D: 201 Created
    end
    Note over D,DB: The patient reads it with GET /api/DigitalPrescription/patient/{id}
```

</details>

<details>
<summary><b>🧪 Uploading a lab result</b></summary>

```mermaid
sequenceDiagram
    autonumber
    actor D as Doctor / Staff
    participant C as TestingController
    participant F as FileService
    participant S as TestingService
    participant DB as SQL Server

    D->>C: POST /api/Testing (title, date, medicalRecordId, file)
    Note right of C: policy CanCreateMedicalRecord
    C->>F: validate file (PDF or image, max 10 MB)
    alt invalid file
        C-->>D: 400
    else valid
        F->>F: save under wwwroot/uploads with a unique name
        C->>S: Add(testing with file path)
        S->>DB: insert Testing
        C-->>D: 201 Created
    end
```

</details>

<details>
<summary><b>💬 Chat: sending a message & receipts</b></summary>

Messages are sent and loaded over **REST**. The SignalR hub delivers the **delivered** and **read** receipts live.

```mermaid
sequenceDiagram
    autonumber
    actor A as Sender
    actor B as Recipient
    participant Hub as ChatHub (/hubs/chat)
    participant C as ChatController
    participant S as MessageService
    participant DB as SQL Server

    A->>Hub: connect (JWT)
    Hub->>Hub: add connection to groups of allowed conversations
    B->>Hub: connect (JWT)

    A->>C: POST /api/Chat/conversations/{id}/messages
    C->>S: SendMessageAsync
    S->>DB: insert Message
    S->>DB: insert MessageStatus = Sent (per recipient)
    C-->>A: 201 message

    B->>C: GET /api/Chat/conversations/{id}/messages
    C-->>B: history (with each message's status)

    B->>Hub: MarkAsDelivered(conversationId, messageId)
    Hub->>S: MarkAsDeliveredAsync
    S->>DB: status = Delivered
    Hub-->>A: MessageDelivered
    B->>Hub: MarkAsRead(conversationId, messageId)
    Hub->>S: MarkAsReadAsync
    S->>DB: status = Read
    Hub-->>A: MessageRead
```

</details>

<details>
<summary><b>🤖 AI specialty recommendation</b></summary>

```mermaid
sequenceDiagram
    autonumber
    actor P as Patient
    participant C as DoctorsAiController
    participant AI as AI model (Hugging Face Space)
    participant K as AiKeepAliveService
    participant DC as DoctorController

    loop every 2 minutes
        K->>AI: ping so the Space stays awake
    end

    P->>C: POST /api/doctors/ai/recommend-by-symptoms (symptoms text)
    C->>AI: POST /predict_specialty
    alt AI unreachable
        C-->>P: 503 AI service is currently unavailable
    else answered
        AI-->>C: predicted specialty
        C-->>P: same status + body from the model
    end
    P->>DC: GET /api/Doctor/search?specialization=...
    DC-->>P: matching doctors
```

</details>

<details>
<summary><b>⏰ Appointment reminders</b></summary>

```mermaid
sequenceDiagram
    autonumber
    participant R as AppointmentReminderBackgroundService
    participant DB as SQL Server
    participant M as Email (SMTP)
    actor P as Patient

    loop every 1 minute
        R->>DB: appointments where ReminderAt <= now and not ReminderSent
        loop each due appointment
            R->>M: send reminder email
            M-->>P: "Your appointment is coming up"
            R->>DB: ReminderSent = true
        end
    end
```

</details>

<details>
<summary><b>🛡️ Doctor verification by an admin</b></summary>

```mermaid
sequenceDiagram
    autonumber
    actor D as Doctor
    actor A as Admin
    participant AC as AdminDashboardController
    participant S as AdminDashboardService
    participant DB as SQL Server

    D->>DB: registers with ID number + ID card images (status Pending)
    A->>AC: GET /api/AdminDashboard/doctors
    AC-->>A: doctors with their documents
    alt documents are valid
        A->>AC: POST /doctors/{id}/verify
        AC->>S: VerifyDoctor
        S->>DB: VerificationStatus = Verified, clear RejectionReason
    else documents are not valid
        A->>AC: POST /doctors/{id}/reject (reason)
        AC->>S: RejectDoctor
        S->>DB: VerificationStatus = Rejected, save reason
    end
    AC-->>A: 200
```

</details>

<details>
<summary><b>🌐 Request pipeline & authorization</b></summary>

```mermaid
sequenceDiagram
    autonumber
    actor U as Client
    participant MW as Middlewares
    participant Auth as Authentication + Authorization
    participant H as SuperAdminAuthorizationHandler
    participant Ctl as Controller
    participant Log as LoggingAsyncMiddleware
    participant DB as SQL Server

    U->>MW: HTTPS request with Bearer token
    MW->>MW: exception handler, HTTPS redirect, forwarded headers
    MW->>Log: start timer
    Log->>Auth: routing, CORS, then auth (skipped for /swagger)
    Auth->>Auth: validate JWT, read roles + permission claims
    Auth->>H: check the endpoint's policy
    alt user is SuperAdmin
        H-->>Auth: every requirement succeeds
    else has the needed permission claim
        Auth-->>Auth: policy succeeds
    else missing claim
        Auth-->>U: 403 Forbidden
    end
    Auth->>Ctl: run the action
    Ctl-->>Log: response
    Log->>DB: save ApiAuditLog (endpoint, status, duration, user, IP)
    Log-->>U: response
    Note over MW,Ctl: Unhandled exceptions become ProblemDetails (GlobalErrorHandling)
```

</details>

<details>
<summary><b>🧱 Data access: Controller → Service → Unit of Work</b></summary>

```mermaid
sequenceDiagram
    autonumber
    participant Ctl as Controller
    participant S as Service (BusinessLayer)
    participant V as FluentValidation
    participant UoW as UnitOfWork
    participant R as GenericRepository<T>
    participant Ctx as ApplicationDbContext
    participant DB as SQL Server

    Ctl->>S: call with a DTO
    S->>V: validate DTO
    S->>UoW: e.g. UoW.Appointments
    UoW->>R: GenericRepository<Appointment>
    R->>Ctx: Add / Update / Find / query
    S->>UoW: SaveChanges() (or Begin/Commit/Rollback)
    UoW->>Ctx: SaveChangesAsync
    Ctx->>DB: SQL
    S-->>Ctl: Result<T> (data or error type)
    Ctl-->>Ctl: map error type to HTTP status
```

</details>

<details>
<summary><b>🚀 Startup & initialization</b></summary>

```mermaid
sequenceDiagram
    autonumber
    participant P as Program.cs
    participant Env as .env file
    participant DI as Service registration
    participant DB as SQL Server
    participant X as medicines.xlsx

    P->>Env: DotNetEnv.Load("../.env")
    P->>DI: API, database, Identity, authorization policies, app services, AutoMapper, Serilog
    P->>DB: apply pending migrations
    P->>DB: seed roles and permission claims
    P->>DB: seed admin user
    P->>DB: seed doctor dashboard test data + test doctor
    P->>X: read medicines (ClosedXML)
    alt file found
        X-->>DB: insert medicines
    else missing
        P->>P: log warning, medicine table stays empty
    end
    P->>P: build middleware pipeline, map controllers + /hubs/chat
    P->>P: start background services (reminders, AI keep-alive)
```

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
| `ChatHub` | `/hubs/chat` | Join conversations and push **delivered** / **read** receipts live (messages themselves are sent and loaded over REST) |

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
