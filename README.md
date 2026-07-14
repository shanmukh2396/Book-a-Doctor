This is the Drive link regarding the documentation of the project.
https://drive.google.com/drive/folders/1MLTuhBKXx4XQcoT5XnJbsmydUAb3fFJ3?usp=sharing


# MedConnect - Book a Doctor App

MedConnect is a full-stack healthcare booking platform designed to streamline patient-to-provider connectivity. By offering dynamic specialist browsing, secure real-time slot scheduling, secure medical record storage, and role-based dashboards, the platform significantly reduces administrative overhead and improves patient-doctor collaboration.

Developed as a modern full-stack web application using the **MERN (MongoDB, Express, React, Node.js)** technology stack.

---

## 👥 Project Team
* **Shanmukha Venkata Vardhan Thatavarthy** (Team Lead)
* **Yemineni Kavya** (Member)

---

## 📂 Phase-Wise Project Documentation
Detailed documentation corresponding to each phase of the project lifecycle has been compiled into the `/documentation` directory:

1. 💡 **[Phase 1: Brainstorming & Ideation](file:///C:/Users/shanm/Desktop/smartbridge%20project/documentation/1_Brainstorming_and_Ideation.md)**
   * Selects problem statement, lists idea brainstorming/prioritization matrix, defines Patient/Doctor/Admin customer problem statements, and Empathy Map Canvas.
2. 📋 **[Phase 2: Requirement Analysis](file:///C:/Users/shanm/Desktop/smartbridge%20project/documentation/2_Requirement_Analysis.md)**
   * System boundaries detailed via Level 0 and Level 1 Data Flow Diagrams (DFD), functional & non-functional requirements catalog, and Agile User Stories backlog.
3. 📐 **[Phase 3: Project Design](file:///C:/Users/shanm/Desktop/smartbridge%20project/documentation/3_Project_Design.md)**
   * Proposed solution parameters, database design mapping (Mongoose models for User, DoctorProfile, Appointment, Document, and Notification), and Technical Architecture definitions.
4. 📅 **[Phase 4: Project Planning](file:///C:/Users/shanm/Desktop/smartbridge%20project/documentation/4_Project_Planning.md)**
   * Product backlog estimates (Story Points), Sprint scheduling tracker (Sprint-1 & Sprint-2 details), team velocity metrics, and burndown chart statistics.
5. 🧪 **[Phase 5: User Acceptance Testing (UAT)](file:///C:/Users/shanm/Desktop/smartbridge%20project/documentation/5_User_Acceptance_Testing.md)**
   * Quality Assurance testing environments, Test Cases (TC-001 through TC-006) verification log, and bug tracking register.

---

## 🛠️ Technology Stack
* **Frontend:** React.js, Vite, Vanilla CSS (Glassmorphism, CSS Variable dynamic themes), Lucide Icons.
* **Backend:** Node.js, Express.js (REST API).
* **Database:** MongoDB (NoSQL), Mongoose ODM.
* **Storage:** Local Filesystem (configured dynamically via Multer).
* **Authentication:** Stateless JSON Web Tokens (JWT), Bcrypt password encryption.

---

## 📂 Folder Structure
```
smartbridge project/
├── backend/
│   ├── config/
│   │   └── db.js            # Mongoose MongoDB connection config
│   ├── middleware/
│   │   └── authMiddleware.js # JWT & Role authorization checks
│   ├── models/
│   │   ├── Appointment.js   # Booking appointments
│   │   ├── DoctorProfile.js # Doctor specialties & available slots
│   │   ├── Document.js      # Patient uploaded medical files metadata
│   │   ├── Notification.js  # Alarm notification logs
│   │   └── User.js          # Main auth accounts (bcrypt pre-save hook)
│   ├── routes/
│   │   ├── admins.js        # Admin endpoints (approvals & statistics)
│   │   ├── auth.js          # Authentication (register, logins, profile check)
│   │   ├── doctors.js       # Doctor controls (slots, review documents, prescriptions)
│   │   └── patients.js      # Patient controls (booking, document uploads, alerts)
│   ├── scripts/
│   │   └── verify_connection_and_auth.js # Database programmatic test validator
│   ├── uploads/             # Physical storage folder for uploaded records
│   ├── .env                 # Environment variables config
│   ├── package.json         # Backend node packages
│   └── server.js            # Express entry application driver
├── frontend/
│   ├── src/
│   │   ├── components/
│   │   │   └── Navbar.jsx   # Role-based dashboard navigation panel
│   │   ├── pages/
│   │   │   ├── AdminDashboard.jsx  # Admin page controls
│   │   │   ├── DoctorDashboard.jsx # Doctor page controls
│   │   │   ├── Login.jsx           # Sign in page
│   │   │   ├── PatientDashboard.jsx# Patient page controls
│   │   │   └── Register.jsx        # Account registration
│   │   ├── App.jsx          # Root client coordinator
│   │   ├── AuthContext.jsx  # React state store for user sessions & JWTs
│   │   ├── index.css        # Glassmorphic custom CSS rules
│   │   └── main.jsx         # App bootstrapping
│   ├── index.html           # Document shell
│   ├── package.json         # Client package dependencies
│   └── vite.config.js       # Vite server proxy configurations
```

---

## 🚀 Setup & Launch Instructions

### Prerequisites
* Install [Node.js](https://nodejs.org/) (v16.0.0 or above).
* Install and run [MongoDB Community Server](https://www.mongodb.com/try/download/community) locally at `mongodb://127.0.0.1:27017`.

### 1. Backend Server Setup
1. Open a terminal and navigate to the backend directory:
   ```bash
   cd backend
   ```
2. Install npm dependencies:
   ```bash
   npm install
   ```
3. Initialize the environment configuration file `.env` (already configured in workspace):
   ```env
   PORT=5000
   MONGO_URI=mongodb://127.0.0.1:27017/book_a_doctor
   JWT_SECRET=supersecretkeyforbookadoctorapp
   ```
4. Start the Express development server:
   ```bash
   npm start
   ```
   *Note: On initial boot, the database automatically seeds a master Administrator account:*
   * **Email:** `admin@doctor.com`
   * **Password:** `adminpassword123`

### 2. Frontend client Setup
1. Open a second terminal and navigate to the frontend directory:
   ```bash
   cd frontend
   ```
2. Install client dependencies:
   ```bash
   npm install
   ```
3. Boot the Vite React client environment:
   ```bash
   npm run dev
   ```
4. Access the web application on: `http://localhost:3000` (or the local numerical address `http://127.0.0.1:3000`).

---

## 🧪 API Verification & Testing

### Programmatic Integration Test
We have implemented a Node.js integration script to test database connectivity, pre-save encryption, model schemas, and login matching.
1. Run the test script inside the `backend` folder:
   ```bash
   node scripts/verify_connection_and_auth.js
   ```
2. On successful verification, the console will print:
   `Backend Integration Code Verification: SUCCESS!`

### Production Frontend Build Check
Verify client files compilation and asset bundles:
```bash
cd frontend
npm run build
```
On successful build, Vite will compile assets into the `/dist` directory.
