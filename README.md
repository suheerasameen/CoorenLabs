# 🚀 Cooren API

**Cooren is an open-source, high-performance, and scalable scraping engine designed to collect, organize, and deliver structured data from across the world of anime, movies, manga, and music — all in one unified ecosystem.**

Developed and maintained by **[CoorenLabs](https://coorenlabs.com)**.

---

## 🔗 Quick Links

* 🌐 **Main Website:** https://coorenlabs.com
* 📘 **Official Documentation:** https://docs.coorenlabs.com

---

## ✨ Features

* 🌍 **Unified Media Ecosystem**

  * ⛩️ Anime Providers & Mappings
  * 📖 Manga Providers (e.g., Mangaball, Atsu)
  * 🍿 Movie & TV Providers
  * 🎵 Music Providers
  * ⚡ Direct Stream Providers

* 🧩 **Open Source**
  Fully open-source and community-driven.

* ⚡ **High Performance**
  Powered by **Bun** and **ElysiaJS** for blazing-fast execution.

* 🧠 **Advanced Scraping**
  Uses Cheerio, Puppeteer, and Axios for handling static + dynamic content.

* 📄 **Built-in Swagger UI**
  Auto-generated OpenAPI documentation.

* 👨‍💻 **Developer Friendly**

  * TypeScript support
  * ESLint configured
  * Modular provider architecture

---

## 🛠️ Tech Stack

* ⚙️ **Runtime:** Bun
* 🚀 **Framework:** ElysiaJS
* 💻 **Language:** TypeScript
* 🔍 **Scraping:** Cheerio, Puppeteer
* 🗄️ **Database/Cache:** Upstash Redis
* ✅ **Validation:** Zod

---

## 🚦 Getting Started

### 📦 Prerequisites

Make sure you have **Bun** installed:

👉 https://bun.sh

---

### 📥 Installation

Clone the repository and install dependencies:

```bash
git clone https://github.com/your-username/cooren-api.git
cd cooren-api
bun install
```

---

### ▶️ Running the Server

Start development server:

```bash
bun run dev
```

With hot reload:

```bash
bun run hot
```

---

### 🏗️ Build for Production

```bash
bun run build:bun   # Optimized build for Bun
bun run build:node  # Compile using TypeScript
```

---

## 📚 API Documentation

* 🌐 Online Docs: https://docs.coorenlabs.com
* 🖥️ Local Docs:

  ```
  http://localhost:<PORT>/docs
  ```

---

## 🏗️ Project Structure

```
src/
├── core/
│   ├── config.ts
│   ├── logger.ts
│   ├── proxyRoutes.ts
│   └── mappingRoutes.ts
│
├── providers/
│   └── (individual providers)
```

---

## 🧩 Creating a New Provider

Each provider should follow this structure:

```
src/providers/<provider-name>/
├── route.ts
├── <provider-name>.ts
└── types.ts
```

---

### 📌 Example: route.ts

```ts
import Elysia from "elysia";
import { FlixHQ } from "./flixhq";

export const flixhqRoutes = new Elysia({ prefix: "/flixhq" })
  .get("/home", async () => {
    return await FlixHQ.home();
  })
  .get("/search/:query", async ({ params: { query } }) => {
    return await FlixHQ.search(query);
  });
```

---

### 📌 Example: Provider Logic

```ts
export class FlixHQ {
  static async home() {
    // scraping logic
    return data;
  }

  static async search(query: string) {
    // search logic
    return data;
  }
}
```

---

### 📌 Example: types.ts

```ts
export interface FlixHQResponse {
  title: string;
  url: string;
}
```

---

## 🧪 Testing & Linting

Run tests:

```bash
bun run test
```

Lint your code:

```bash
bun run lint
bun run lint:fix
```

---

## 🤝 Contributing

Contributions are welcome!
Feel free to fork the repo, create a branch, and submit a PR.

---

## 📄 License

This project is open-source and available under the **GPL-3.0 license**.

---

## 💡 Maintained By

**CoorenLabs**
🌐 https://coorenlabs.com

---
