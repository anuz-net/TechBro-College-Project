# TechBro — Ecommerce Site for Tech Gadgets

[![Build Status](https://img.shields.io/badge/build-passing-brightgreen)](#) [![License: MIT](https://img.shields.io/badge/license-MIT-blue.svg)](#) [![Demo](https://img.shields.io/badge/demo-live-blueviolet)](#)

A small, fast ecommerce site for buying and selling tech gadgets. Built with plain HTML, Tailwind CSS, vanilla JavaScript, PHP backend, and MySQL — optimized for simplicity and easy deployment.

## Key Features
- Product catalog with categories, filters, and search
- Product detail pages with variants and specs
- Shopping cart and checkout (server‑side PHP)
- User auth (email/password)
- Admin area to manage products and orders
- Stripe / PayPal payment hooks (placeholder integration)
- Responsive UI (Tailwind CSS)
- Simple REST endpoints in PHP
- Lightweight, easy to customize

## Demo & Screenshots
Screenshots: [![Screenshot-2025-09-17-104227.png](https://i.postimg.cc/7hzTLmDp/Screenshot-2025-09-17-104227.png)](https://postimg.cc/YLpSnNv3)

## Tech Stack
[![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat&logo=html5&logoColor=white)](https://developer.mozilla.org/en-US/docs/Web/HTML) [![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-06B6D4?style=flat&logo=tailwindcss&logoColor=white)](https://tailwindcss.com) [![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat&logo=javascript&logoColor=black)](https://developer.mozilla.org/en-US/docs/Web/JavaScript)  
[![PHP](https://img.shields.io/badge/PHP-777BB4?style=flat&logo=php&logoColor=white)](https://www.php.net) [![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=flat&logo=mysql&logoColor=white)](https://www.mysql.com)  
[![Stripe](https://img.shields.io/badge/Stripe-635bff?style=flat&logo=stripe&logoColor=white)](https://stripe.com) [![PayPal](https://img.shields.io/badge/PayPal-003087?style=flat&logo=paypal&logoColor=white)](https://www.paypal.com)  
[![Node.js](https://img.shields.io/badge/Node.js-339933?style=flat&logo=nodedotjs&logoColor=white)](https://nodejs.org) [![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat&logo=docker&logoColor=white)](https://www.docker.com)

## Getting Started (Local)

Prerequisites
- Node.js (for Tailwind) and npm
- PHP >= 8.0
- MySQL
- (optional) Docker & docker-compose

Clone
```bash
git clone https://github.com/your-org/TechBro.git
cd TechBro
```

Install frontend tools (Tailwind)
```bash
cd frontend
npm install
# dev build (watch)
npm run dev
# production build
npm run build
```

Backend & DB
1. Create a MySQL database:
    - Example: CREATE DATABASE techbro;
2. Copy and edit backend/.env (or config.php)
```
APP_URL=http://localhost:8000
DB_HOST=127.0.0.1
DB_NAME=techbro
DB_USER=root
DB_PASS=your_password
STRIPE_KEY=sk_test_...
```
3. Import DB schema (if provided):
```bash
mysql -u root -p techbro < db/schema.sql
```

Run (development)
- Serve static frontend files from frontend/dist (or use Vite) and run PHP backend:
```bash
# from project root (simple PHP dev server)
php -S localhost:8000 -t backend/public
# or use your Apache / Nginx setup
```
- Ensure Tailwind dev build is running (npm run dev) to regenerate CSS while editing.

Build & Run (production)
- Build Tailwind assets:
```bash
cd frontend && npm run build
```
- Deploy PHP app to your preferred host (Apache, Nginx + PHP-FPM). Point document root to backend/public.

Docker (optional)
- Example Docker + docker-compose can be added to containerize PHP + MySQL + a Node service for building assets.

## API Endpoints (examples)
- GET /api/products
- GET /api/products/:id
- POST /api/cart
- POST /api/checkout
- POST /api/auth/login
- POST /api/auth/register

Adjust endpoints and request/response shapes to match your implementation.

## Testing
- Frontend: manual UI testing, Lighthouse
- Backend: PHPUnit (if you add tests)
- Basic commands:
```bash
# run PHP unit tests (if present)
vendor/bin/phpunit
```

## Project Structure (recommended)
- frontend/ — HTML, Tailwind config, JS, build scripts
- backend/ — PHP app, public/, src/, vendor/
- docs/ — screenshots, design notes
- db/ — schema.sql, seed data
- docker/ — Dockerfiles and compose

## Contributing
1. Fork the repo
2. Create a branch: git checkout -b feature/your-feature
3. Implement, add tests, run linters/build
4. Open a PR with description and screenshots

Follow coding and commit guidelines in CONTRIBUTING.md.

## License
MIT — see LICENSE file.

## Notes
Replace placeholders (repo URL, environment values, payment keys) with real values. Keep secrets out of version control (use .env and .env.example).