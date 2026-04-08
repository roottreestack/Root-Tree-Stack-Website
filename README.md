# Root Tree Stack (RTS) - Company Website

[![Lighthouse Performance](https://img.shields.io/badge/Performance-98-brightgreen)](https://developers.google.com/web/tools/lighthouse)
[![Lighthouse Accessibility](https://img.shields.io/badge/Accessibility-93-brightgreen)](https://developers.google.com/web/tools/lighthouse)
[![Lighthouse Best Practices](https://img.shields.io/badge/Best%20Practices-100-brightgreen)](https://developers.google.com/web/tools/lighthouse)
[![Lighthouse SEO](https://img.shields.io/badge/SEO-100-brightgreen)](https://developers.google.com/web/tools/lighthouse)

**Live Website:** [https://roottreestack.pythonanywhere.com/](https://roottreestack.pythonanywhere.com/)

---

## 📖 Overview

**Root Tree Stack (RTS)** is a complete, production-ready company website built with **Django 5.x** (Python) and a fully custom **Admin CMS Dashboard**. It features a modern dark-themed public frontend and a powerful backend interface that lets you manage every piece of content without touching Django’s built-in admin.

The website is optimized for performance (98/100 on Lighthouse), accessibility (93/100), best practices (100/100), and SEO (100/100). It serves as a portfolio, service catalog, tech showcase, team directory, and blog platform – all fully manageable through an intuitive dashboard.

---

## 🚀 Services We Provide

Root Tree Stack offers a wide range of technology and creative services. All services are fully manageable via the CMS dashboard – you can add, edit, categorize, and reorder them at any time.

### Core Service Categories (Examples)

| Category | Example Services |
|----------|------------------|
| **Web Development** | Custom Web Applications, E‑commerce Solutions, CMS Development, API Integration |
| **Mobile Development** | iOS & Android Apps, Cross‑Platform (Flutter/React Native), App Maintenance |
| **UI/UX Design** | Responsive Web Design, User Interface Design, Prototyping & Wireframing |
| **Cloud & DevOps** | AWS/GCP/Azure Deployment, CI/CD Pipelines, Containerization (Docker) |
| **Software Consulting** | Technical Audit, Architecture Design, Team Training |
| **Digital Marketing** | SEO, Content Strategy, Analytics Setup |

> 💡 *The exact services displayed on the website can be customized from the dashboard → Services section.*

---

## ✨ Complete Website Features

### 🧩 Public Frontend

| Page | Features |
|------|----------|
| **Home** | Hero section with CTA, dynamic previews of Services, Portfolio, Tech Stack, Team, Blog, and a contact CTA. Section visibility can be toggled from the dashboard. |
| **About** | Mission & Vision, Company Story, Timeline of milestones, Achievements/Stats (e.g., projects completed, clients). |
| **Services** | Catalog of all services with category filters. Each service has a dedicated detail page with full description and icon. |
| **Portfolio** | Project showcase with category filters (e.g., Web, Mobile, Design). Each project includes images, description, technologies used, and live/demo links. |
| **Technologies** | Tech stack grouped by category (Frontend, Backend, Databases, DevOps, etc.). Displays logos, names, and descriptions. |
| **Team** | Grid of team members with photos, names, roles, social links, and short bios. |
| **Blog** | Blog list with search, category filter, and tag filter. Each post supports rich content rendered via Monaco Editor (code‑friendly). |
| **Contact** | Contact form (name, email, message) that stores submissions in the database. All messages are viewable in the dashboard inbox. |

### 🔐 Custom Authentication System

- **Fully custom** session‑based authentication (does NOT use `django.contrib.auth`).
- **User roles:** `super_admin`, `admin`, `editor`, `user`.
- **Decorators:** `@login_required`, `@staff_required`, `@super_admin_required`.
- Auth middleware injects `request.current_user` for every request.

### 🎛️ Admin CMS Dashboard (Custom)

Access at `/dashboard/` after logging in. Provides complete control over all website content.

| Dashboard Section | Capabilities |
|------------------|---------------|
| **Statistics Overview** | Counts of posts, projects, messages, team members, users, etc. |
| **Services** | Add/Edit/Delete services. Manage categories, descriptions, icons, and order. |
| **Portfolio** | Add/Edit/Delete projects. Upload images, assign categories, set live links. |
| **Blog** | Full CRUD for posts. Monaco Editor integration for writing code‑rich articles. Manage categories & tags. |
| **Team** | Add/Edit/Delete team members. Upload profile photos, add social links. |
| **Technologies** | Manage tech stack items. Group by category (e.g., languages, frameworks). |
| **About Page Editor** | Edit mission, vision, company story, timeline events, achievement stats. |
| **Homepage Settings** | Toggle visibility of sections (services preview, portfolio, tech stack, team, blog, CTA). Edit hero text and buttons. |
| **Messages Inbox** | View, mark as read, delete contact form submissions. |
| **User Management** | Create, edit, delete users. Assign roles (`super_admin`, `admin`, `editor`, `user`). |
| **Site Settings** | Branding (logo, site name), contact info (email, phone, address), social media links, SEO meta tags. |
| **Activity Log** | Track all admin actions (who created/edited/deleted what). |

### 🎨 Design System

- **Theme:** Dark (`#0a0e0f` background, `#131c1f` for cards)
- **Accent Color:** Green (`#22c55e`)
- **Typography:** Inter (body) + JetBrains Mono (code blocks)
- **Components:** Cards, badges, panels, data tables, toggle switches, filter bars, responsive grid.

---

## 🛠️ Tech Stack

| Component | Technology |
|-----------|------------|
| Backend | Django 5.x (Python 3.11) |
| Database | SQLite (via Django ORM – easily swappable with PostgreSQL/MySQL) |
| Static Files | WhiteNoise (with compressed manifest storage) |
| Media Uploads | Django file storage (`/media/`) |
| Frontend | Vanilla HTML5, CSS3, JavaScript (ES6) |
| Code Editor (Blog) | Monaco Editor (CDN) |
| Fonts | Google Fonts – Inter & JetBrains Mono |
| Session Management | Django DB sessions (7‑day cookie lifetime) |
| CSRF Protection | Django built‑in, with trusted origins for Replit/PythonAnywhere |
| Deployment | PythonAnywhere (or any WSGI server) |

---

## 📂 Project Structure

rts-website/
├── rts/ # Django project config (settings, urls, wsgi)
├── apps/
│ ├── core/ # Custom User model, auth middleware, site settings, activity log
│ ├── home/ # Homepage (hero + section visibility toggles)
│ ├── about/ # About page (mission, vision, timeline, achievements)
│ ├── services/ # Service catalog with categories
│ ├── portfolio/ # Portfolio projects with categories
│ ├── technologies/ # Tech stack grouped by category
│ ├── team/ # Team members
│ ├── blog/ # Blog posts, categories, tags, Monaco rendering
│ └── contact/ # Contact form & message storage
├── dashboard/ # Custom CMS dashboard (full CRUD, settings, activity log)
├── templates/ # All HTML templates
│ ├── base.html # Public site base layout
│ ├── dashboard/base.html # Dashboard layout
│ ├── home/, about/, services/, portfolio/, technologies/, team/, blog/, contact/
│ ├── auth/ # Login template
│ └── errors/ # 404, 500 error pages
├── static/
│ ├── css/main.css # Complete dark theme CSS (green #22c55e accent)
│ └── js/main.js # Navbar, filters, animations, Monaco initializer
├── media/ # User-uploaded images (team photos, project images, blog thumbnails)
├── manage.py
├── seed.py # Initial data seed script (populates demo services, portfolio, etc.)
└── requirements.txt


---

## 🔧 Installation & Setup

### Prerequisites

- Python 3.11+
- pip
- SQLite (included with Python)

### Steps

1. **Clone the repository**
   ```bash
   git clone https://github.com/your-org/rts-website.git
   cd rts-website

## Create a virtual environment
python -m venv venv
source venv/bin/activate   # Linux/Mac
venv\Scripts\activate      # Windows

## Install dependencies
pip install -r requirements.txt

Run migrations
python manage.py migrate
Seed initial data (optional but recommended)


python seed.py
This creates demo services, portfolio projects, team members, blog posts, and a default admin user.

Create super admin manually (if not using seed)


python manage.py shell
python
from apps.core.models import User
User.objects.create_super_admin(
    email="admin@example.com",
    username="admin",
    password="securepassword",
    role="super_admin"
)
Run the development server


python manage.py runserver 0.0.0.0:8000
The site will be available at http://localhost:8000

Environment Variables
Create a .env file in the project root (optional, but recommended for production):


⚠️ Important: Change these credentials immediately after first login in a production environment.

📊 Performance & Optimization
Lighthouse scores captured on Desktop (emulated) with Lighthouse 13.0.1:

Metric	Value
Performance	98
Accessibility	93
Best Practices	100
SEO	100
First Contentful Paint (FCP)	0.8 s
Largest Contentful Paint (LCP)	0.9 s
Total Blocking Time (TBT)	40 ms
Cumulative Layout Shift (CLS)	0.049
Speed Index (SI)	1.2 s
Key Optimizations Implemented
Efficient cache lifetimes (saves ~367 KiB)

Optimized image delivery (saves ~330 KiB)

Eliminated render‑blocking requests (saves ~620 ms)

Minimal unused JavaScript (62 KiB savings)

Proper width/height attributes on images to prevent layout shifts

Long main‑thread tasks minimized (only 2 found)

Non‑composited animations avoided

🚢 Deployment
The website is ready for deployment on any WSGI‑compatible platform:

PythonAnywhere (current hosting)
Upload the project to PythonAnywhere.

Set up a web app with manual configuration (WSGI).

Point to the project’s wsgi.py.

Set DEBUG=False and configure ALLOWED_HOSTS.

Run python manage.py migrate on the server.

Collect static files: python manage.py collectstatic.

Other Platforms
Replit: Uses PORT env var (default 24480) and trusts replit.dev domains.

Heroku / Render / DigitalOcean: Use Gunicorn + WhiteNoise. Set up PostgreSQL instead of SQLite for production.

Example gunicorn command:

bash
gunicorn rts.wsgi:application --bind 0.0.0.0:$PORT
📝 License
This project is proprietary. All rights reserved.
For licensing inquiries, please contact Root Tree Stack directly.

🙏 Acknowledgements
Django & Python communities

Monaco Editor (Microsoft)

Google Fonts

WhiteNoise for static file serving

Lighthouse for performance insights

📬 Contact
For support, feature requests, or business inquiries:

Website: https://roottreestack.pythonanywhere.com/

Email: roottreestack@gmail.com 

Contact Form: Available on the public website

Built with ❤️ using Django & custom CMS – Root Tree Stack
