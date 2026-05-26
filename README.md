# 🌐 My Personal Introductory WebPage

A personal presentation website built with **Astro** and **Tailwind CSS**. Designed to showcase who I am, my technical skills, projects, and ways to get in touch — with a focus on performance, clean design, and ease of maintenance.

---

## 🚀 Tech Stack

| Technology | Role |
|---|---|
| [Astro](https://astro.build) | Main framework (SSG) |
| [Tailwind CSS](https://tailwindcss.com) | Utility-first styling |
| HTML / CSS / JS | Site foundation |
| [Node.js](https://nodejs.org) | Development environment |

---

## 📁 Project Structure

```
presentation-page/
├── public/
│   └── favicon.svg
├── src/
│   ├── components/
│   │   ├── Hero.astro          # Main presentation section
│   │   ├── About.astro         # About me + personal description
│   │   ├── Skills.astro        # Tech stack and technologies
│   │   ├── Projects.astro      # GitHub project cards
│   │   └── Contact.astro       # Contact links and social media
│   ├── layouts/
│   │   └── Layout.astro        # Base layout with head and nav
│   └── pages/
│       └── index.astro         # Main page
├── astro.config.mjs
├── tailwind.config.mjs
├── tsconfig.json
├── package.json
├── README.md
└── CLAUDE.md
```

---

## 📄 Site Sections

- **Hero** — Name, professional title, and main CTA
- **About** — Personal bio and background
- **Skills** — Technologies and tools I work with
- **Projects** — Cards highlighting featured GitHub projects
- **Contact** — Email, LinkedIn, GitHub, and other links

---

## ⚙️ Local Setup

### Prerequisites

- Node.js v18 or higher
- npm v9 or higher

### Steps

```bash
# 1. Clone the repository
git clone https://github.com/bcesano20/presentation-page.git
cd presentation-page

# 2. Install dependencies
npm install

# 3. Start the development server
npm run dev
```

The site will be available at `http://localhost:4321`

### Other Commands

```bash
# Build for production
npm run build

# Preview the production build
npm run preview

# Check for type errors
npm run astro check
```

---

## 🏗️ Deployment

The site is optimized for static deployment. Currently is deployed in Vercel.
