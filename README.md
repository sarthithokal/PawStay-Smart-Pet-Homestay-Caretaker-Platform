# PawStay: Smart Pet Homestay & Caretaker Platform
 PawStay is a full-stack, enterprise-style web portal designed to bridge the structural gap in the pet care ecosystem. Built using a secure **Three-Tier Architecture**, the platform connects pet owners with verified, background-approved caretakers, automating scheduling metrics, state lifecycle management, and transaction routing.

##  Core Architectural Layout

The platform is engineered using a decoupled, modular design to ensure high maintainability, clear separation of concerns, and robust security parameters:

---

##  Primary Functional Profiles

The system handles access control matrices seamlessly across three distinct authentication scopes:

### 1. System Administrator Module
* **Governance Filters:** Evaluates and executes automated approvals/rejections for new caretaker onboarding structures.
* **Operational Monitoring:** Real-time system logs monitoring concurrent platform bookings, traffic telemetry, and platform security flags.

### 2. Pet Owner (Client) Module
* **Entity Management:** CRUD configuration allowing clients to register pet profiles, upload vaccination timelines, and update behavioral attributes.
* **Dynamic Search Architecture:** Filters caretakers by availability windows, services offered, and historical customer feedback ratings.

### 3. Caretaker (Provider) Module
* **State Machine Schedulers:** Real-time dashboard to accept, queue, or reject booking requests, which automatically locks dates upon approval.
* **Telemetry Reporting:** Provides automated structured updates to owners regarding daily feeding, exercise, and health tracking vectors.

---

##  Technology Stack

* **Frontend Environment:** HTML5, CSS3, JavaScript (ES6+), Bootstrap Framework (Mobile-First Responsive Architecture)
* **Backend Runtime:** C# Development Lifecycle via .NET Framework 4.5 (ASP.NET Web Forms)
* **Data Transit Layer:** ADO.NET Architecture
* **Database Infrastructure:** Microsoft SQL Server (Relational RDBMS Engine)
* **Development IDE:** Visual Studio 2019

---

##  Deep Technical Engineering Metrics

###  SQL Injection Defense via Parameterized Layering
To secure user credentials and systemic data assets against injection exploits, the system strictly prohibits raw string concatenations for database queries. All data processing requests are marshaled using **Parameterized SQL Commands**:

```csharp
using (SqlConnection conn = new SqlConnection(connectionString)) {
    string query = "SELECT UserID, PasswordHash, Role FROM Users WHERE Email = @Email";
    using (SqlCommand cmd = new SqlCommand(query, conn)) {
        // Data input is strictly evaluated as a literal vector, neutralizing inline execution scripts
        cmd.Parameters.AddWithValue("@Email", txtEmail.Text.Trim());
        conn.Open();
        // Read logic execution...
    }
