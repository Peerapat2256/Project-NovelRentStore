#  NovelRentStore - Modern E-Book Rental Platform

<!-- <div align="center">
  <img src="[ใส่ลิงก์รูปภาพหน้าจอเว็บสวยๆ ของคุณที่นี่ เช่น อัปโหลดรูปใน issue แล้วเอาลิงก์มาวาง]" alt="NovelRentStore Preview" width="100%">
</div> -->

> ** Notice:** The source code is temporarily kept private until the final university project defense is completed. However, you are highly encouraged to explore the live demo and system architecture below!

##  Live Demo
[![Website](https://img.shields.io/badge/Website-Visit_Live_Demo-4F8B82?style=for-the-badge&logo=google-chrome&logoColor=white)](https://p66-novelrent-web.csmsu.net/)

---

## 📖 About The Project
**NovelRentStore** is a full-stack digital book and comic rental platform. It was built with a focus on delivering a premium user experience and high-performance backend processing. 

The highlight of the platform is its **Custom Reading Engine**, which processes heavy PDF files into highly optimized WebP images on the fly, delivering a seamless reading experience comparable to top-tier commercial platforms.

##  Key Features
- **Advanced Reader Engine:** A fully custom-built reader supporting Single, Double, and Long-strip (Webtoon) layouts with dynamic zooming and progression tracking.
- **High-Performance Processing:** Built a Golang worker-pool pipeline that concurrently extracts, compresses, and streams PDF pages to the cloud, reducing processing time by up to 80%.
- **Seamless UX/UI:** Beautiful, responsive, and interactive design built with Nuxt 3 and Tailwind CSS.
- **Smart Book Management:** Intelligent renting system with expiration tracking, auto-resume reading progress, and real-time status updates.

## 🛠️ Tech Stack & Technologies Used

### Frontend
![Nuxt.js](https://img.shields.io/badge/Nuxt_3-002E3B?style=for-the-badge&logo=nuxtdotjs&logoColor=#00DC82)
![Vue.js](https://img.shields.io/badge/Vue_3-35495E?style=for-the-badge&logo=vuedotjs&logoColor=4FC08D)
![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-38B2AC?style=for-the-badge&logo=tailwind-css&logoColor=white)

### Backend & Infrastructure
![Go](https://img.shields.io/badge/Go_1.20-00ADD8?style=for-the-badge&logo=go&logoColor=white)
![Supabase](https://img.shields.io/badge/Supabase-3ECF8E?style=for-the-badge&logo=supabase&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-316192?style=for-the-badge&logo=postgresql&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2CA5E0?style=for-the-badge&logo=docker&logoColor=white)

## 🧠 System Architecture Highlight
One of the core technical achievements of this project is the **PDF-to-WebP Concurrency Pipeline**:
1. When an admin uploads a book, the Go backend triggers a non-blocking background job.
2. A pool of **8 concurrent workers** executes `pdftoppm` to extract pages.
3. The extracted pages are dynamically compressed into `WebP` format and streamed directly to **Supabase Storage**.
4. The frontend client polls the progress via a lightweight API, providing live, real-time upload progress to the user without locking the main thread.

---
*Designed & Developed by Peerapat*
