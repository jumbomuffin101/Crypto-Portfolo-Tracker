# Crypto Portfolio Tracker

Live Demo:  
https://blueprint-crypto.netlify.app

Crypto Portfolio Tracker is a full stack RSA encryption and decryption service built as a submission for SecureLog’s Blueprint Developer Challenge. The project demonstrates secure API design, persistent logging, and clean frontend and backend integration using a modern serverless stack.

Rather than focusing only on cryptography, the project emphasizes building a realistic system around encryption, including observability, persistence, and deployment best practices.

---

## Overview

Crypto Portfolio Tracker allows users to:

- Encrypt plaintext using an RSA public key  
- Decrypt ciphertext using the corresponding private key  
- View, paginate, and clear encryption request logs stored in PostgreSQL  
- Check real time API health  
- Interact with a clean, cyber styled user interface  

The goal of the project is to showcase how cryptographic operations can be exposed safely through an API while maintaining transparency, traceability, and system reliability.

---

## Data Flow

1. User submits plaintext or ciphertext from the frontend  
2. Backend performs RSA encryption or decryption using Node’s crypto module  
3. Request metadata is persisted to PostgreSQL  
4. API response is returned and rendered in the UI  

This mirrors real world secure services where cryptographic operations must be auditable and observable.

---

## Features

- **RSA Encryption and Decryption**  
  Public key encryption and private key decryption using standard cryptographic primitives  

- **Persistent Logging**  
  All requests are stored in PostgreSQL with pagination and clearing support  

- **Health Monitoring**  
  Real time API status endpoint for basic observability  

- **Serverless Architecture**  
  Backend implemented using Netlify Functions for scalability and simplicity  

- **Clean UI**  
  Cyber themed frontend designed for clarity and ease of use  

---

## Tech Stack

### Frontend
- React  
- TypeScript  
- Vite  
- Deployed on Netlify  

### Backend
- Node.js via Netlify Functions  
- Native Node crypto module for RSA operations  

### Database
- PostgreSQL hosted on Neon  
- Persistent, searchable request logs  

### Development and Tooling
- Docker Compose for local development  
- GitHub Actions for CI  
- ESLint for frontend linting  
- Ruff for backend linting  

---

## Repository Structure

crypto-portfolio-tracker/
├── .github/
│ └── workflows/
│ ├── web-lint.yml
│ └── server-lint.yml
├── server/
│ ├── app/
│ │ └── main.py
│ ├── Dockerfile
│ └── requirements.txt
├── web/
│ ├── src/
│ ├── package.json
│ ├── Dockerfile
│ └── netlify/functions/api.mjs
├── docker-compose.yml
└── README.md
