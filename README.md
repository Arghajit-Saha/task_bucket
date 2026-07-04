<p align="center">
  <img src="client/public/edc_dark.png" alt="EDC NIT Durgapur Logo" width="150" />
</p>

<h1 align="center">Task Bucket</h1>

<p align="center">
  A full-stack task management and collaboration platform built for the Entrepreneurship Development Cell (EDC), NIT Durgapur. Designed for cross-functional workflows, speed, modularity, and secure team collaboration.
</p>

<p align="center">
  <a href="https://task-bucket.vercel.app"><strong>View Live Demo »</strong></a>
  ·
  <a href="https://github.com/Subhadip006/task_bucket/issues">Report Bug</a>
  ·
  <a href="https://github.com/Subhadip006/task_bucket/issues">Request Feature</a>
</p>

---

## Table of Contents

- [About The Project](#about-the-project)
- [Key Features](#key-features)
- [Tech Stack](#tech-stack)
- [Project Structure](#project-structure)
- [Getting Started](#getting-started)
  - [Prerequisites](#prerequisites)
  - [Installation](#installation)
  - [Environment Variables](#environment-variables)
- [Running the Project](#running-the-project)
- [Available Scripts](#available-scripts)
- [Deployment](#deployment)
- [License](#license)
- [Contact](#contact)

---

## About The Project

Task Bucket is a complete, modular task management solution developed for the Entrepreneurship Development Cell (EDC) at NIT Durgapur. Structured as a scalable monorepo with a modern React and Vite frontend paired with a robust Node.js and Express backend, it simplifies club operations, member task distribution, and cross-departmental collaboration. The platform focuses on high performance, strict data security, and seamless workflow management across multiple technical and creative domains.

---

## Key Features

- **Multi-Domain & Multi-Skill Support**: Members can select multiple domains during registration (Web Development, Content Writing, Graphic Designing, Video Editing, General). The platform dynamically adapts task visibility, filtering, and assignment pipelines across all selected skill areas.
- **Role-Based Access Control & Admin Panel**: A dedicated administrative dashboard allows club maintainers to review and approve new user registrations, inspect domain distributions, and manage organization-wide tasks.
- **Flexible Task Assignment**: Tasks can be assigned to individual members or distributed to entire domain groups. Includes public and private visibility toggles to separate personal drafts from collaborative team tasks.
- **Interactive Discussion Threads**: Every task features an integrated commenting and discussion system, facilitating real-time communication, status updates, and peer feedback.
- **Real-Time Task Notifications**: Built-in notification popups and status trackers keep team members updated on new assignments, progress changes, and deadlines.
- **Input Validation & Security**: Strong backend validation prevents malformed or malicious data submissions, ensuring database integrity and secure collaboration.
- **Rate Limiting & Abuse Prevention**: Custom rate-limiting middleware protects backend API endpoints against excessive requests, spam, and brute-force attempts.
- **Responsive Dark-Mode UI**: Built with Tailwind CSS and Lucide Icons, providing a clean, modern, and fully responsive user interface optimized for desktop and mobile workflows.

---

## Tech Stack

| Layer | Technology |
| --- | --- |
| Frontend | React, Vite, Tailwind CSS, Lucide Icons |
| Backend | Node.js, Express.js, MongoDB, Mongoose |
| Authentication | JSON Web Tokens (JWT) with Multi-Domain Claims |
| Security | Custom Middleware, API Rate Limiting, Input Validation |
| Deployment | Vercel Monorepo Configuration |

---

## Project Structure

The repository is organized as a unified monorepo containing distinct client and backend applications:

```text
task_bucket/
├── client/          # React frontend (Vite + Tailwind CSS)
├── backend/         # Express backend (Controllers, Routes, Models, Security)
├── CHANGELOG.md     # Feature and release history
├── LICENSE.md       # MIT License
├── MULTIPLE_DOMAINS_FEATURE.md # Detailed technical documentation on multi-domain support
├── package.json     # Root workspace configuration
└── README.md        # Project documentation
```

---

## Getting Started

Follow these steps to set up a local development environment.

### Prerequisites

Ensure you have the following software installed on your local machine:

- Node.js (v18.x or later recommended)
- npm (bundled with Node.js)
- MongoDB instance (local or Atlas connection string)

### Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/Subhadip006/task_bucket.git
   cd task_bucket
   ```

2. Install root workspace dependencies:
   ```bash
   npm install
   ```

3. Install frontend dependencies:
   ```bash
   cd client
   npm install
   ```

4. Install backend dependencies:
   ```bash
   cd ../backend
   npm install
   ```

### Environment Variables

The project requires specific environment variables for database connectivity, authentication, and API routing.

**Backend Configuration (`/backend`)**:
Create a `.env` file inside the `backend/` directory and configure the following parameters:

```env
PORT=5000
DATABASE_URL="your_mongodb_connection_string"
JWT_SECRET="your_strong_jwt_secret_key"
```

**Frontend Configuration (`/client`)**:
Create a `.env` file inside the `client/` directory to connect the frontend to your local backend server:

```env
VITE_API_BASE_URL="http://localhost:5000/api"
```

---

## Running the Project

To run the full stack locally, open two separate terminal windows for the frontend and backend services.

1. **Start the Backend Server** (from the `backend/` directory):
   ```bash
   npm run start
   ```
   The Express API server will start on `http://localhost:5000`.

2. **Start the Frontend Server** (from the `client/` directory):
   ```bash
   npm run dev
   ```
   The Vite development server will start on `http://localhost:5173` (or the port specified by Vite).

---

## Available Scripts

| Location | Command | Description |
| --- | --- | --- |
| client | `npm run dev` | Starts the Vite frontend development server |
| client | `npm run build` | Compiles and optimizes the frontend for production deployment |
| backend | `npm run start` | Starts the Express backend API server |

---

## Deployment

The monorepo is structured for seamless automated deployment on Vercel:

1. Push your changes to a GitHub repository.
2. Import the repository into your Vercel account.
3. Vercel automatically detects the monorepo structure and configures build settings via `vite.config.js`.
4. Add all required environment variables from your `.env` files into the Vercel Project Settings prior to initiating the production deployment.

---

## License

Distributed under the MIT License. See `LICENSE.md` for more information.