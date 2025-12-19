# Blueprint Crypto Challenge

A full stack RSA encryption and decryption service with persistent, searchable logs.  
Built as a submission for SecureLog’s Blueprint Developer Challenge.

**Live demo:** https://blueprint-crypto.netlify.app

---

## Overview

**Blueprint Crypto** is a small but complete encryption platform designed to demonstrate secure API design, real world persistence, and clean frontend and backend integration.

At a high level, the app allows users to:
- Encrypt plaintext using an RSA public key
- Decrypt ciphertext using the corresponding private key
- View, paginate, and clear request logs stored in PostgreSQL
- Check real time API health
- Interact with a clean, cyber styled user interface

The focus of this project was not just encryption, but building a realistic system around it with logging, observability, and deployment best practices.

---

## Tech stack

**Frontend**
- React with Vite and TypeScript
- Deployed on Netlify

**Backend**
- Node.js serverless functions via Netlify Functions
- Uses Node’s native `crypto` module for RSA encryption and decryption

**Database**
- PostgreSQL hosted on Neon Cloud
- Stores persistent, searchable request logs

**Dev and tooling**
- Docker Compose for local development
- GitHub Actions for automated linting
- ESLint for frontend checks
- Ruff for backend checks

---

## Production setup

**Frontend**
- Hosted on Netlify  
- URL: https://blueprint-crypto.netlify.app

**API**
- Exposed via Netlify Functions  
- Routes available under `/api/v1/*`

**Database**
- Neon hosted PostgreSQL
- Connected securely via environment variables

The frontend communicates with the backend through Netlify’s serverless proxy, keeping API paths stable and simple.

---

**Repository Structure**
blueprint-crypto
├── .github/
│   └── workflows/
│       ├── web-lint.yml
│       └── server-lint.yml
├── server/
│   ├── app/
│   │   └── main.py
│   ├── Dockerfile
│   └── requirements.txt
├── web/
│   ├── src/
│   ├── package.json
│   ├── Dockerfile
│   └── netlify/functions/api.mjs
├── docker-compose.yml
└── README.md

---

**What I would improve with more time**
- Add authentication and user scoped logs
- Add request rate limiting and abuse protection
- Add structured log filtering in the UI
- Add unit and integration tests for crypto and database layers
- Add key validation and formatting helpers in the frontend
