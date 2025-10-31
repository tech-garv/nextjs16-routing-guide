v# 🚀 Next.js 16 App Router — Complete Routing Guide

> Learn every essential **Next.js 16 App Router concept** in one place — from **Basic Routing** to **Dynamic**, **Nested**, and **Docs-style Catch-All Routing**.

![Next.js](https://img.shields.io/badge/Next.js-16.0-black?style=for-the-badge&logo=next.js)
![React](https://img.shields.io/badge/React-18.3-blue?style=for-the-badge&logo=react)
![TypeScript](https://img.shields.io/badge/TypeScript-5.6-blue?style=for-the-badge&logo=typescript)

---

## 📚 Table of Contents
1. [About This Project](#-about-this-project)
2. [Tech Stack](#-tech-stack)
3. [Folder Structure](#-folder-structure)
4. [Routing Concepts](#-routing-concepts)
   - [1️⃣ Basic Routing](#1️⃣-basic-routing)
   - [2️⃣ Dynamic Routing](#2️⃣-dynamic-routing)
   - [3️⃣ Nested Routing](#3️⃣-nested-routing)
   - [4️⃣ Nested Dynamic Routing](#4️⃣-nested-dynamic-routing)
   - [5️⃣ Catch-All Routes](#5️⃣-catch-all-routes)
   - [6️⃣ Docs Subpages Example](#6️⃣-docs-subpages-example)
5. [How Routing Works Internally](#-how-routing-works-internally)
6. [Getting Started](#-getting-started)
7. [Useful Commands](#-useful-commands)
8. [Resources](#-resources)
9. [Author](#-author)

---

## 🧠 About This Project
This repository demonstrates **how routing works in the Next.js 16 App Router** (stable and improved in v16).  
Understanding these patterns helps you build scalable apps such as:
- 🧾 Documentation sites  
- 🛍️ E-commerce platforms  
- 📊 Dashboards  
- 📰 Blogs  

---

## 🧩 Tech Stack
- ⚡ **Next.js 16 (App Router)**
- ⚛️ **React 18**
- 💙 **TypeScript**
- 🎨 **Tailwind CSS** *(optional for styling)*

---

## 🗂 Folder Structure
```bash
app/
│
├── page.tsx               → Home Page (/)
│
├── about/
│   └── page.tsx           → /about
│
├── products/
│   ├── page.tsx           → /products
│   └── [id]/
│       └── page.tsx       → /products/1
│
├── dashboard/
│   ├── layout.tsx         → Shared layout (Navbar/Sidebar)
│   ├── page.tsx           → /dashboard
│   └── settings/
│       └── page.tsx       → /dashboard/settings
│
└── docs/
    └── [[...slugs]]/
        └── page.tsx       → /docs, /docs/setup, /docs/api/ref
🔗 Routing Concepts
1️⃣ Basic Routing
Every folder inside the app/ directory that contains a page.tsx file becomes a route.

Example

bash
Copy code
app/about/page.tsx → /about
tsx
Copy code
export default function AboutPage() {
  return <h1>About Us</h1>;
}
✅ No react-router needed — folder = route.

2️⃣ Dynamic Routing
Use square brackets [param] to create dynamic routes.

Example

bash
Copy code
app/products/[id]/page.tsx → /products/1
tsx
Copy code
export default function Product({ params }: { params: { id: string } }) {
  return <h1>Product ID: {params.id}</h1>;
}
✅ Use case: product pages, user profiles, etc.

3️⃣ Nested Routing
Create multi-level pages by nesting folders.

Example

bash
Copy code
app/dashboard/settings/page.tsx → /dashboard/settings
✅ Use case: dashboards with sub-pages.

4️⃣ Nested Dynamic Routing
Combine nested and dynamic segments.

Example

bash
Copy code
app/users/[userid]/posts/[postid]/page.tsx → /users/1/posts/5
tsx
Copy code
export default function Post({
  params,
}: {
  params: { userid: string; postid: string };
}) {
  return (
    <h1>
      User {params.userid}'s Post {params.postid}
    </h1>
  );
}
✅ Use case: social media feeds, blog comments, etc.

5️⃣ Catch-All Routes
Use [...slug] or [[...slug]] for variable-length paths.

Example

lua
Copy code
app/docs/[[...slugs]]/page.tsx
tsx
Copy code
export default function Docs({ params }: { params: { slugs?: string[] } }) {
  if (!params.slugs) return <h1>Welcome to Docs</h1>;
  return <h1>Docs Path: {params.slugs.join(" / ")}</h1>;
}
✅ Use case: documentation, breadcrumbs, or flexible URLs.

6️⃣ Docs Subpages Example
All of these URLs are handled by one file:

bash
Copy code
/docs
/docs/getting-started
/docs/setup/advanced
/docs/api/reference
➡️ app/docs/[[...slugs]]/page.tsx

⚙️ How Routing Works Internally
Concept	Description
app/	Root of App Router
page.tsx	Rendered UI for the route
[param]	Dynamic segment
layout.tsx	Shared layout across nested routes
[[...slug]]	Optional catch-all segment

🧰 Getting Started
bash
Copy code
# Clone this repository
git clone https://github.com/garvpuri/nextjs16-routing-guide.git

# Navigate to folder
cd nextjs16-routing-guide

# Install dependencies
npm install

# Run development server
npm run dev
Then open http://localhost:3000 in your browser.

🧩 Useful Commands
Command	Description
npm run dev	Start local development server
npm run build	Build for production
npm start	Run production build
npx create-next-app@latest	Create new Next.js 16 project

🌐 Resources
📘 Official Next.js 16 Docs

🎥 Traversy Media – Next.js 16 Crash Course

💻 Next.js GitHub Examples

🧑‍💻 Author
👋 Garv Puri
Aspiring Full-Stack Developer | Passionate about Next.js, Node.js, and AI Integration

💼 GitHub: github.com/tech-garv
