# 🐾 PurrfectMatch – Cat Adoption Platform (Full Stack)

**PurrfectMatch** is a modern, secure, and scalable **full-stack cat adoption platform** designed to connect loving adopters with verified pet owners through a trusted moderation system.

Built with **NestJS** on the backend and **Next.js (React)** on the frontend, this project showcases **real-world full-stack engineering practices**, including authentication with **HTTP-only cookies**, **role-based access control (RBAC)**, data validation with **Zod**, and a clean UI using **shadcn/ui**.

---

## 🌍 Why PurrfectMatch?

Pet adoption platforms often suffer from fake listings, weak moderation, insecure authentication, and poor role separation. **PurrfectMatch** solves these problems by introducing:

* Verified & moderated cat listings
* Clear role separation (Admin, Moderator, Owner, Adopter)
* Secure authentication using HTTP-only cookies
* Ownership-based access control
* Clean, accessible, and modern UI

This project is ideal as a **portfolio-grade full-stack application** or a foundation for a production-ready startup.

---

## 🧱 Tech Stack

### 🔹 Frontend

* **Next.js 14 (App Router)**
* **React 18**
* **TypeScript**
* **shadcn/ui** (Radix + Tailwind CSS)
* **Zod** (schema validation)
* **React Hook Form**
* **Axios / Fetch API**

### 🔹 Backend

* **NestJS**
* **TypeScript**
* **PostgreSQL**
* **TypeORM**
* **JWT Authentication**
* **HTTP-only Cookies**
* **RBAC (Role-Based Access Control)**

---

## 👥 User Roles

| Role          | Responsibilities                                |
| ------------- | ----------------------------------------------- |
| **ADMIN**     | Full system control, manage users & analytics   |
| **MODERATOR** | Review and approve cat listings, handle reports |
| **OWNER**     | List cats for adoption and manage requests      |
| **ADOPTER**   | Browse cats and submit adoption requests        |

---

## 🔐 Authentication & Security

* Login & Signup via `/auth/login` and `/auth/signup`
* JWT stored in **HTTP-only cookies** (XSS-safe)
* Role embedded in JWT payload
* Route protection via Guards (backend) & Middleware (frontend)
* Password hashing with bcrypt

---

## 🛡️ Authorization (RBAC)

Access control is enforced using:

* `@Roles()` decorator
* `JwtAuthGuard`
* `RolesGuard`

Example:

```ts
@Roles(Role.ADMIN, Role.MODERATOR)
@UseGuards(JwtAuthGuard, RolesGuard)
@Patch('/cats/:id/approval')
approveCat() {}
```

Additionally, **ownership checks** ensure users can only modify resources they own.

---

## 🐱 Core Features

### Cat Listings

* Create, edit, delete cat listings (Owners)
* Approval workflow: `PENDING → APPROVED / REJECTED`
* Public browsing of approved cats
* Filter by breed, age, location

### Adoption Workflow

* Adoption requests by adopters
* Approval/rejection by owners
* Adoption status tracking

### Moderation & Safety

* Report cats or users
* Moderator review panel
* Admin-level user blocking

---

## 🧾 Frontend Highlights

* App Router–based layout
* Role-aware UI rendering
* Form validation with **Zod**
* Accessible UI components using **shadcn/ui**
* Protected routes & server-side auth checks

---

## 🗂️ Database Entities

* **User** – authentication, roles
* **Cat** – adoption listings
* **Adoption** – adoption requests
* **Report** – moderation system
* **RefreshToken** (optional)

All entities use:

* UUID primary keys
* Proper relational mapping
* Audit timestamps

---

## 🧠 Problems This Project Solves

### ❌ Common Problems

* Fake or spam adoption listings
* No moderation before publishing
* Weak authentication systems
* No role-based access control
* Insecure frontend token storage

### ✅ PurrfectMatch Solutions

* Moderator approval before public listing
* Strong RBAC with backend enforcement
* Secure HTTP-only cookie authentication
* Ownership-based resource control
* Scalable full-stack architecture

---

## 🚀 Getting Started (Local Development)

### Backend

```bash
cd backend
npm install
npm run start:dev
```

### Frontend

```bash
cd frontend
npm install
npm run dev
```

Create `.env` files for both frontend and backend as required.

---

## 📈 Future Improvements

* Email notifications
* Image upload (Cloudinary / S3)
* Real-time chat between adopter & owner
* Admin analytics dashboard
* Mobile app support

---

## 🎯 Who Is This Project For?

* Full-stack developers
* Computer science students
* Final-year project submissions
* Portfolio & job applications
* Startup MVP foundation

---

## 📄 License

This project is open-source and free to use for learning and educational purposes.

---

## 🙌 Author

Built as a **real-world full-stack application** focusing on clean architecture, security, and scalability.

Happy adopting 😺❤️
