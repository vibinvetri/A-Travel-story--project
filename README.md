# Travel Stories — MERN App

A simple, interview‑friendly MERN project where users can create, edit, delete, and browse personal travel stories with images. Auth uses JWT in **httpOnly** cookies (with an optional Authorization header fallback). Clean folder structure, easy setup, and clear API.

---

## ✨ Features

* **Auth**: Signup, Login, Logout with JWT (httpOnly cookies) + header fallback
* **Stories**: Create, Read, Update, Delete (CRUD)
* **Images**: Upload via Multer (local or cloud provider)
* **Dates**: Add a travel date per story
* **Search & Filter**: Text search, date-range filter
* **Favorites**: Pin stories to top
* **Responsive UI**: Modern

---

## 🧰 Tech Stack

**Frontend**: React, React Router, Axios, Tailwind (or CSS), Vite/Create React App

**Backend**: Node.js, Express.js, MongoDB (Mongoose), Multer, JSON Web Token (JWT), Cookie‑Parser, CORS

**Storage**: Local `/uploads` (default) or Cloud (e.g., Cloudinary / S3)

---

## 🔐 Auth (JWT + httpOnly Cookies)

* On **login/signup**, server issues a JWT and sets it as an **httpOnly** cookie: `Set-Cookie: token=...; HttpOnly; Secure; SameSite=Lax`.
* Client calls protected routes with credentials (Axios `withCredentials: true`).
* **Fallback**: if needed, client may send `Authorization: Bearer <token>` header (e.g., for mobile or cross‑site cases).
* Server middleware verifies the token, attaches `req.user`, continues.
* **Logout** clears the cookie.

---


## 🧠 Simple Architecture

* **Client**: React Router for pages; AuthContext stores `user` and calls `/auth/me` on load; Axios instance adds `withCredentials`.
* **Server**: Express routes → controllers → services; `auth` middleware checks JWT; `error` middleware standardizes errors.
* **DB**: Mongoose models for `User` and `Story` (title, content, date, tags, imageUrl, pinned, ownerId, timestamps).

-
