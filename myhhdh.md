# UOP API — Complete Testing Progress Tracker

> **Base URL:** `http://localhost:5000/api`
> **Last Updated:** 2026-06-09
> **Status Legend:** ✅ Pass | ❌ Fail | ⏳ Pending | 🔄 In Progress

---

## Summary

| Module | Total Endpoints | ✅ Pass | ❌ Fail | ⏳ Pending |
|--------|----------------|---------|---------|-----------|
| Health Check | 1 | ⏳ | ⏳ | 1 |
| Auth | 9 | ⏳ | ⏳ | 9 |
| LMS – Courses | 6 | ⏳ | ⏳ | 6 |
| LMS – Enrollment | 1 | ⏳ | ⏳ | 1 |
| LMS – Attendance (Legacy) | 2 | ⏳ | ⏳ | 2 |
| LMS – Sessions | 6 | ⏳ | ⏳ | 6 |
| LMS – Student Self-Mark | 2 | ⏳ | ⏳ | 2 |
| LMS – Assignments | 5 | ⏳ | ⏳ | 5 |
| LMS – Assignment Grading | 3 | ⏳ | ⏳ | 3 |
| LMS – Quizzes | 8 | ⏳ | ⏳ | 8 |
| LMS – Performance | 2 | ⏳ | ⏳ | 2 |
| LMS – Certificates | 5 | ⏳ | ⏳ | 5 |
| LMS – Certificate Template | 2 | ⏳ | ⏳ | 2 |
| LMS – LMS Documents | 4 | ⏳ | ⏳ | 4 |
| LMS – File Signing | 1 | ⏳ | ⏳ | 1 |
| LMS – Admin | 8 | ⏳ | ⏳ | 8 |
| Documents | 6 | ⏳ | ⏳ | 6 |
| Dashboard | 2 | ⏳ | ⏳ | 2 |
| Notifications | 3 | ⏳ | ⏳ | 3 |
| **TOTAL** | **76** | **0** | **0** | **76** |

---

## 1. Health Check

| # | Method | Endpoint | Auth | Status | Notes |
|---|--------|----------|------|--------|-------|
| 1 | GET | `/api/health` | None | ⏳ | Server health check |

### Test Results
- **1.1** `GET /api/health` → ⏳ Pending

---

## 2. Auth Module (`/api/auth`)

| # | Method | Endpoint | Auth | Roles | Status | Notes |
|---|--------|----------|------|-------|--------|-------|
| 2.1 | POST | `/api/auth/register/admin` | None (Rate Limited) | — | ⏳ | Register first admin |
| 2.2 | POST | `/api/auth/register` | None (Rate Limited) | — | ⏳ | Register student/teacher |
| 2.3 | POST | `/api/auth/login` | None (Rate Limited) | — | ⏳ | Login, returns JWT |
| 2.4 | POST | `/api/auth/refresh` | None (Rate Limited) | — | ⏳ | Refresh access token |
| 2.5 | POST | `/api/auth/logout` | Bearer JWT | — | ⏳ | Logout |
| 2.6 | GET | `/api/auth/me` | Bearer JWT | — | ⏳ | Get current user profile |
| 2.7 | PATCH | `/api/auth/profile` | Bearer JWT | — | ⏳ | Update profile |
| 2.8 | PATCH | `/api/auth/password` | Bearer JWT | — | ⏳ | Change password |
| 2.9 | GET | `/api/auth/users` | Bearer JWT | admin | ⏳ | List all users |

### Test Results
- **2.1** `POST /api/auth/register/admin` → ⏳ Pending
- **2.2** `POST /api/auth/register` → ⏳ Pending
- **2.3** `POST /api/auth/login` → ⏳ Pending
- **2.4** `POST /api/auth/refresh` → ⏳ Pending
- **2.5** `POST /api/auth/logout` → ⏳ Pending
- **2.6** `GET /api/auth/me` → ⏳ Pending
- **2.7** `PATCH /api/auth/profile` → ⏳ Pending
- **2.8** `PATCH /api/auth/password` → ⏳ Pending
- **2.9** `GET /api/auth/users` → ⏳ Pending

---

## 3. LMS Module (`/api/lms`)

### 3A. Courses

| # | Method | Endpoint | Auth | Roles | Status | Notes |
|---|--------|----------|------|-------|--------|-------|
| 3A.1 | GET | `/api/lms/courses` | Bearer JWT | admin, teacher, student | ⏳ | List all courses |
| 3A.2 | GET | `/api/lms/courses/:id` | Bearer JWT | admin, teacher, student | ⏳ | Get single course |
| 3A.3 | POST | `/api/lms/courses` | Bearer JWT | admin, teacher | ⏳ | Create course |
| 3A.4 | PATCH | `/api/lms/courses/:id` | Bearer JWT | admin, teacher | ⏳ | Update course |
| 3A.5 | PATCH | `/api/lms/courses/:id/draft` | Bearer JWT | admin, teacher | ⏳ | Save course as draft |
| 3A.6 | DELETE | `/api/lms/courses/:id` | Bearer JWT | admin | ⏳ | Delete course |

### Test Results – Courses
- **3A.1** `GET /api/lms/courses` → ⏳ Pending
- **3A.2** `GET /api/lms/courses/:id` → ⏳ Pending
- **3A.3** `POST /api/lms/courses` → ⏳ Pending
- **3A.4** `PATCH /api/lms/courses/:id` → ⏳ Pending
- **3A.5** `PATCH /api/lms/courses/:id/draft` → ⏳ Pending
- **3A.6** `DELETE /api/lms/courses/:id` → ⏳ Pending

---

### 3B. Enrollment

| # | Method | Endpoint | Auth | Roles | Status | Notes |
|---|--------|----------|------|-------|--------|-------|
| 3B.1 | POST | `/api/lms/courses/:id/enroll` | Bearer JWT | admin, teacher | ⏳ | Enroll a student |

### Test Results – Enrollment
- **3B.1** `POST /api/lms/courses/:id/enroll` → ⏳ Pending

---

### 3C. Attendance (Legacy)

| # | Method | Endpoint | Auth | Roles | Status | Notes |
|---|--------|----------|------|-------|--------|-------|
| 3C.1 | POST | `/api/lms/attendance` | Bearer JWT | admin, teacher | ⏳ | Mark attendance |
| 3C.2 | GET | `/api/lms/courses/:id/attendance` | Bearer JWT | admin, teacher | ⏳ | Get course attendance |

### Test Results – Attendance (Legacy)
- **3C.1** `POST /api/lms/attendance` → ⏳ Pending
- **3C.2** `GET /api/lms/courses/:id/attendance` → ⏳ Pending

---

### 3D. Sessions

| # | Method | Endpoint | Auth | Roles | Status | Notes |
|---|--------|----------|------|-------|--------|-------|
| 3D.1 | POST | `/api/lms/courses/:courseId/sessions` | Bearer JWT | admin, teacher | ⏳ | Create session (supports file upload) |
| 3D.2 | GET | `/api/lms/courses/:courseId/sessions` | Bearer JWT | admin, teacher, student | ⏳ | Get course sessions |
| 3D.3 | PATCH | `/api/lms/sessions/:id` | Bearer JWT | admin, teacher | ⏳ | Update session |
| 3D.4 | PATCH | `/api/lms/sessions/:id/toggle` | Bearer JWT | admin, teacher | ⏳ | Toggle session active/inactive |
| 3D.5 | GET | `/api/lms/sessions/:id/attendance` | Bearer JWT | admin, teacher | ⏳ | Get session attendance |
| 3D.6 | PATCH | `/api/lms/sessions/:id/attendance/:studentId` | Bearer JWT | admin, teacher | ⏳ | Override student attendance |

### Test Results – Sessions
- **3D.1** `POST /api/lms/courses/:courseId/sessions` → ⏳ Pending
- **3D.2** `GET /api/lms/courses/:courseId/sessions` → ⏳ Pending
- **3D.3** `PATCH /api/lms/sessions/:id` → ⏳ Pending
- **3D.4** `PATCH /api/lms/sessions/:id/toggle` → ⏳ Pending
- **3D.5** `GET /api/lms/sessions/:id/attendance` → ⏳ Pending
- **3D.6** `PATCH /api/lms/sessions/:id/attendance/:studentId` → ⏳ Pending

---

### 3E. Student Self-Mark Attendance

| # | Method | Endpoint | Auth | Roles | Status | Notes |
|---|--------|----------|------|-------|--------|-------|
| 3E.1 | POST | `/api/lms/sessions/:id/attend` | Bearer JWT | student | ⏳ | Student marks own attendance |
| 3E.2 | GET | `/api/lms/courses/:courseId/attendance/mine` | Bearer JWT | student | ⏳ | Student gets own attendance summary |

### Test Results – Student Self-Mark
- **3E.1** `POST /api/lms/sessions/:id/attend` → ⏳ Pending
- **3E.2** `GET /api/lms/courses/:courseId/attendance/mine` → ⏳ Pending

---

### 3F. Assignments

| # | Method | Endpoint | Auth | Roles | Status | Notes |
|---|--------|----------|------|-------|--------|-------|
| 3F.1 | POST | `/api/lms/assignments` | Bearer JWT | admin, teacher | ⏳ | Create assignment (file upload) |
| 3F.2 | GET | `/api/lms/courses/:courseId/assignments` | Bearer JWT | admin, teacher, student | ⏳ | Get course assignments |
| 3F.3 | PATCH | `/api/lms/assignments/:id` | Bearer JWT | admin, teacher | ⏳ | Update assignment |
| 3F.4 | DELETE | `/api/lms/assignments/:id` | Bearer JWT | admin, teacher | ⏳ | Delete assignment |
| 3F.5 | POST | `/api/lms/assignments/:id/submit` | Bearer JWT | student | ⏳ | Submit assignment (file upload) |

### Test Results – Assignments
- **3F.1** `POST /api/lms/assignments` → ⏳ Pending
- **3F.2** `GET /api/lms/courses/:courseId/assignments` → ⏳ Pending
- **3F.3** `PATCH /api/lms/assignments/:id` → ⏳ Pending
- **3F.4** `DELETE /api/lms/assignments/:id` → ⏳ Pending
- **3F.5** `POST /api/lms/assignments/:id/submit` → ⏳ Pending

---

### 3G. Assignment Grading

| # | Method | Endpoint | Auth | Roles | Status | Notes |
|---|--------|----------|------|-------|--------|-------|
| 3G.1 | PATCH | `/api/lms/submissions/:assignmentId/grade/:studentId` | Bearer JWT | admin, teacher | ⏳ | Grade a submission |
| 3G.2 | GET | `/api/lms/assignments/:id/submissions` | Bearer JWT | admin, teacher | ⏳ | Get all submissions for assignment |
| 3G.3 | GET | `/api/lms/assignments/:id/submissions/mine` | Bearer JWT | student | ⏳ | Student gets own submission |

### Test Results – Assignment Grading
- **3G.1** `PATCH /api/lms/submissions/:assignmentId/grade/:studentId` → ⏳ Pending
- **3G.2** `GET /api/lms/assignments/:id/submissions` → ⏳ Pending
- **3G.3** `GET /api/lms/assignments/:id/submissions/mine` → ⏳ Pending

---

### 3H. Quizzes

| # | Method | Endpoint | Auth | Roles | Status | Notes |
|---|--------|----------|------|-------|--------|-------|
| 3H.1 | POST | `/api/lms/courses/:courseId/quizzes` | Bearer JWT | admin, teacher | ⏳ | Create quiz |
| 3H.2 | GET | `/api/lms/courses/:courseId/quizzes` | Bearer JWT | admin, teacher, student | ⏳ | Get course quizzes |
| 3H.3 | PATCH | `/api/lms/quizzes/:id` | Bearer JWT | admin, teacher | ⏳ | Update quiz |
| 3H.4 | POST | `/api/lms/quizzes/:id/questions` | Bearer JWT | admin, teacher | ⏳ | Add question to quiz |
| 3H.5 | PATCH | `/api/lms/questions/:id` | Bearer JWT | admin, teacher | ⏳ | Update quiz question |
| 3H.6 | PATCH | `/api/lms/quizzes/:id/publish` | Bearer JWT | admin, teacher | ⏳ | Publish quiz |
| 3H.7 | POST | `/api/lms/quizzes/:id/start` | Bearer JWT | student | ⏳ | Start quiz attempt |
| 3H.8 | POST | `/api/lms/quizzes/:id/submit` | Bearer JWT | student | ⏳ | Submit quiz attempt |
| 3H.9 | GET | `/api/lms/quizzes/:id/results` | Bearer JWT | admin, teacher | ⏳ | Get quiz results |
| 3H.10 | GET | `/api/lms/quizzes/:id/attempts/mine` | Bearer JWT | student | ⏳ | Student gets own attempts |

### Test Results – Quizzes
- **3H.1** `POST /api/lms/courses/:courseId/quizzes` → ⏳ Pending
- **3H.2** `GET /api/lms/courses/:courseId/quizzes` → ⏳ Pending
- **3H.3** `PATCH /api/lms/quizzes/:id` → ⏳ Pending
- **3H.4** `POST /api/lms/quizzes/:id/questions` → ⏳ Pending
- **3H.5** `PATCH /api/lms/questions/:id` → ⏳ Pending
- **3H.6** `PATCH /api/lms/quizzes/:id/publish` → ⏳ Pending
- **3H.7** `POST /api/lms/quizzes/:id/start` → ⏳ Pending
- **3H.8** `POST /api/lms/quizzes/:id/submit` → ⏳ Pending
- **3H.9** `GET /api/lms/quizzes/:id/results` → ⏳ Pending
- **3H.10** `GET /api/lms/quizzes/:id/attempts/mine` → ⏳ Pending

---

### 3I. Performance

| # | Method | Endpoint | Auth | Roles | Status | Notes |
|---|--------|----------|------|-------|--------|-------|
| 3I.1 | GET | `/api/lms/courses/:courseId/performance` | Bearer JWT | admin, teacher | ⏳ | Get course performance stats |
| 3I.2 | GET | `/api/lms/courses/:courseId/performance/mine` | Bearer JWT | student | ⏳ | Student gets own performance |

### Test Results – Performance
- **3I.1** `GET /api/lms/courses/:courseId/performance` → ⏳ Pending
- **3I.2** `GET /api/lms/courses/:courseId/performance/mine` → ⏳ Pending

---

### 3J. Certificates

| # | Method | Endpoint | Auth | Roles | Status | Notes |
|---|--------|----------|------|-------|--------|-------|
| 3J.1 | GET | `/api/lms/certificates/verify/:code` | None (Public) | — | ⏳ | Verify certificate by code |
| 3J.2 | GET | `/api/lms/certificates/verify/:code/pdf` | None (Public) | — | ⏳ | Download certificate PDF (public) |
| 3J.3 | GET | `/api/lms/certificates/mine` | Bearer JWT | student | ⏳ | Student gets own certificates |
| 3J.4 | GET | `/api/lms/certificates/:id/access` | Bearer JWT | admin, teacher, student | ⏳ | Get certificate access URL |
| 3J.5 | POST | `/api/lms/courses/:courseId/certificates/generate/:studentId` | Bearer JWT | admin, teacher | ⏳ | Generate certificate for student |
| 3J.6 | POST | `/api/lms/courses/:courseId/certificates/generate-all` | Bearer JWT | admin, teacher | ⏳ | Generate certificates for all students |
| 3J.7 | GET | `/api/lms/courses/:courseId/certificates` | Bearer JWT | admin, teacher | ⏳ | Get all certificates for course |

### Test Results – Certificates
- **3J.1** `GET /api/lms/certificates/verify/:code` → ⏳ Pending
- **3J.2** `GET /api/lms/certificates/verify/:code/pdf` → ⏳ Pending
- **3J.3** `GET /api/lms/certificates/mine` → ⏳ Pending
- **3J.4** `GET /api/lms/certificates/:id/access` → ⏳ Pending
- **3J.5** `POST /api/lms/courses/:courseId/certificates/generate/:studentId` → ⏳ Pending
- **3J.6** `POST /api/lms/courses/:courseId/certificates/generate-all` → ⏳ Pending
- **3J.7** `GET /api/lms/courses/:courseId/certificates` → ⏳ Pending

---

### 3K. Certificate Template

| # | Method | Endpoint | Auth | Roles | Status | Notes |
|---|--------|----------|------|-------|--------|-------|
| 3K.1 | GET | `/api/lms/courses/:courseId/certificate-template` | Bearer JWT | admin, teacher, student | ⏳ | Get certificate template |
| 3K.2 | POST | `/api/lms/courses/:courseId/certificate-template` | Bearer JWT | admin, teacher | ⏳ | Save/upload certificate template (logo upload) |

### Test Results – Certificate Template
- **3K.1** `GET /api/lms/courses/:courseId/certificate-template` → ⏳ Pending
- **3K.2** `POST /api/lms/courses/:courseId/certificate-template` → ⏳ Pending

---

### 3L. LMS Documents

| # | Method | Endpoint | Auth | Roles | Status | Notes |
|---|--------|----------|------|-------|--------|-------|
| 3L.1 | POST | `/api/lms/courses/:courseId/documents` | Bearer JWT | admin, teacher | ⏳ | Upload course document |
| 3L.2 | GET | `/api/lms/courses/:courseId/documents` | Bearer JWT | admin, teacher, student | ⏳ | Get course documents |
| 3L.3 | DELETE | `/api/lms/documents/:id` | Bearer JWT | admin, teacher | ⏳ | Delete course document |
| 3L.4 | GET | `/api/lms/documents/:id/access` | Bearer JWT | admin, teacher, student | ⏳ | Get document access URL |

### Test Results – LMS Documents
- **3L.1** `POST /api/lms/courses/:courseId/documents` → ⏳ Pending
- **3L.2** `GET /api/lms/courses/:courseId/documents` → ⏳ Pending
- **3L.3** `DELETE /api/lms/documents/:id` → ⏳ Pending
- **3L.4** `GET /api/lms/documents/:id/access` → ⏳ Pending

---

### 3M. File Signing

| # | Method | Endpoint | Auth | Roles | Status | Notes |
|---|--------|----------|------|-------|--------|-------|
| 3M.1 | POST | `/api/lms/files/sign` | Bearer JWT | admin, teacher, student | ⏳ | Get signed URL for a file |

### Test Results – File Signing
- **3M.1** `POST /api/lms/files/sign` → ⏳ Pending

---

### 3N. LMS Admin Routes

| # | Method | Endpoint | Auth | Roles | Status | Notes |
|---|--------|----------|------|-------|--------|-------|
| 3N.1 | GET | `/api/lms/admin/stats` | Bearer JWT | admin | ⏳ | Get admin stats |
| 3N.2 | GET | `/api/lms/admin/users` | Bearer JWT | admin | ⏳ | Get all users (admin) |
| 3N.3 | PATCH | `/api/lms/admin/users/:id/role` | Bearer JWT | admin | ⏳ | Update user role |
| 3N.4 | DELETE | `/api/lms/admin/users/:id` | Bearer JWT | admin | ⏳ | Deactivate user |
| 3N.5 | GET | `/api/lms/admin/courses` | Bearer JWT | admin | ⏳ | Get all courses (admin) |
| 3N.6 | DELETE | `/api/lms/admin/courses/:id` | Bearer JWT | admin | ⏳ | Delete course (admin) |
| 3N.7 | GET | `/api/lms/admin/certificates` | Bearer JWT | admin | ⏳ | Get all certificates (admin) |
| 3N.8 | PATCH | `/api/lms/admin/certificates/:id/revoke` | Bearer JWT | admin | ⏳ | Revoke certificate |

### Test Results – LMS Admin
- **3N.1** `GET /api/lms/admin/stats` → ⏳ Pending
- **3N.2** `GET /api/lms/admin/users` → ⏳ Pending
- **3N.3** `PATCH /api/lms/admin/users/:id/role` → ⏳ Pending
- **3N.4** `DELETE /api/lms/admin/users/:id` → ⏳ Pending
- **3N.5** `GET /api/lms/admin/courses` → ⏳ Pending
- **3N.6** `DELETE /api/lms/admin/courses/:id` → ⏳ Pending
- **3N.7** `GET /api/lms/admin/certificates` → ⏳ Pending
- **3N.8** `PATCH /api/lms/admin/certificates/:id/revoke` → ⏳ Pending

---

## 4. Documents Module (`/api/documents`)

| # | Method | Endpoint | Auth | Roles | Status | Notes |
|---|--------|----------|------|-------|--------|-------|
| 4.1 | GET | `/api/documents` | Bearer JWT | admin, teacher, student | ⏳ | List all documents |
| 4.2 | GET | `/api/documents/:id` | Bearer JWT | admin, teacher, student | ⏳ | Get single document |
| 4.3 | POST | `/api/documents/upload` | Bearer JWT | admin, teacher | ⏳ | Upload document (file upload) |
| 4.4 | PUT | `/api/documents/:id/lifecycle` | Bearer JWT | admin | ⏳ | Update document lifecycle |
| 4.5 | GET | `/api/documents/:id/access` | Bearer JWT | admin, teacher, student | ⏳ | Get presigned URL |
| 4.6 | DELETE | `/api/documents/:id` | Bearer JWT | admin, teacher | ⏳ | Delete document |

### Test Results – Documents
- **4.1** `GET /api/documents` → ⏳ Pending
- **4.2** `GET /api/documents/:id` → ⏳ Pending
- **4.3** `POST /api/documents/upload` → ⏳ Pending
- **4.4** `PUT /api/documents/:id/lifecycle` → ⏳ Pending
- **4.5** `GET /api/documents/:id/access` → ⏳ Pending
- **4.6** `DELETE /api/documents/:id` → ⏳ Pending

---

## 5. Dashboard Module (`/api/dashboard`)

| # | Method | Endpoint | Auth | Roles | Status | Notes |
|---|--------|----------|------|-------|--------|-------|
| 5.1 | GET | `/api/dashboard` | Bearer JWT | admin, teacher, student | ⏳ | Get dashboard stats (role-based) |
| 5.2 | GET | `/api/dashboard/activities` | Bearer JWT | admin, teacher | ⏳ | Get recent activity logs |

### Test Results – Dashboard
- **5.1** `GET /api/dashboard` → ⏳ Pending
- **5.2** `GET /api/dashboard/activities` → ⏳ Pending

---

## 6. Notifications Module (`/api/notifications`)

| # | Method | Endpoint | Auth | Roles | Status | Notes |
|---|--------|----------|------|-------|--------|-------|
| 6.1 | GET | `/api/notifications` | Bearer JWT | all | ⏳ | Get user notifications |
| 6.2 | PATCH | `/api/notifications/read-all` | Bearer JWT | all | ⏳ | Mark all notifications as read |
| 6.3 | PATCH | `/api/notifications/:id/read` | Bearer JWT | all | ⏳ | Mark single notification as read |

### Test Results – Notifications
- **6.1** `GET /api/notifications` → ⏳ Pending
- **6.2** `PATCH /api/notifications/read-all` → ⏳ Pending
- **6.3** `PATCH /api/notifications/:id/read` → ⏳ Pending

---

## Test Run History

| Date | Run By | Total | Pass | Fail | Notes |
|------|--------|-------|------|------|-------|
| — | — | — | — | — | No runs yet |

---

## Known Issues / Bugs Found

_None yet — will be updated as testing progresses._

---

## How to Update This File

When a test is run, update the status:
- Change `⏳ Pending` → `✅ Pass` if the endpoint returns expected response
- Change `⏳ Pending` → `❌ Fail` if the endpoint returns error or unexpected response
- Add notes in the **Notes** column (e.g., error message, status code received)
- Update the **Summary** table counts at the top
- Add a row in **Test Run History**
