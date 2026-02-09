# Secure Message Exchange

**Live Demo:** [https://secure-message-exchange.netlify.app/](https://secure-message-exchange.netlify.app/)

A full-stack encrypted messaging platform demonstrating end-to-end encryption using RSA public-key cryptography. Built to understand how secure messaging systems work under the hood, with emphasis on auditability, observability, and production deployment practices.

---

## Overview

Secure Message Exchange allows users to:
- **Encrypt messages** using RSA public-key cryptography
- **Decrypt messages** with corresponding private keys
- **Audit encryption operations** through persistent PostgreSQL logs
- **Monitor system health** via real-time API status endpoints

The project emphasizes **building a complete system around encryption** - not just implementing crypto algorithms, but handling persistence, observability, deployment, and user experience.

---

## Why I Built This

I wanted to understand how end-to-end encrypted messaging platforms like Signal and WhatsApp work. Rather than just reading about RSA encryption, I built a working system that demonstrates:

- How public/private key pairs enable secure communication
- Why audit logging matters in security-critical systems
- How to deploy cryptographic services reliably
- Best practices for serverless security architecture

---

## Key Features

### Security
- RSA-2048 public-key encryption
- Server-side key generation (demo purposes - production would use client-side)
- Secure message encryption/decryption workflows

### Observability
- Persistent request logging in PostgreSQL
- Paginated log viewer with search
- Real-time API health monitoring
- Request metadata tracking (timestamps, operation types)

### Infrastructure
- Serverless backend (Netlify Functions)
- Containerized local development (Docker Compose)
- Automated CI/CD (GitHub Actions)
- PostgreSQL persistence (Neon)

### User Experience
- Clean, cyber-themed React interface
- Real-time encryption/decryption feedback
- Log management (view, paginate, clear)

---

## Tech Stack

**Frontend:**
- React + TypeScript
- Vite (build tool)
- Deployed on Netlify

**Backend:**
- Node.js via Netlify Functions
- Native `crypto` module for RSA operations
- RESTful API design

**Database:**
- PostgreSQL (Neon hosting)
- Stores encryption request logs

**DevOps:**
- Docker Compose for local development
- GitHub Actions for CI/CD
- ESLint + Ruff for code quality

---

## Architecture
```
User Input (Plaintext)
      ↓
React Frontend
      ↓
Netlify Function (Serverless)
      ↓
RSA Encryption (Node crypto)
      ↓
PostgreSQL (Log Request)
      ↓
Return Encrypted Message
```

---

## Local Development

### Prerequisites
- Node.js 18+
- Docker (for PostgreSQL)

### Setup
```bash
# Clone the repo
git clone https://github.com/jumbomuffin101/Secure-Message-Exchange.git
cd Secure-Message-Exchange

# Start PostgreSQL
docker-compose up -d

# Install dependencies
cd web && npm install
cd ../server && npm install

# Set up environment variables
# Create .env file with DATABASE_URL

# Run locally
npm run dev
```

---

## What I Learned

### Technical
- How RSA public-key cryptography works in practice
- Tradeoffs between client-side and server-side key generation
- Why audit logging is critical for security systems
- Serverless deployment patterns and cold start optimization

### System Design
- How to build observable systems (logging, health checks, monitoring)
- Database schema design for time-series audit data
- API design for cryptographic operations
- Error handling for security-critical workflows

### DevOps
- Containerization for consistent local development
- CI/CD best practices for serverless deployments
- Environment variable management for sensitive data

---

## Future Improvements

- [ ] Client-side key generation (more secure)
- [ ] Message persistence (encrypted storage)
- [ ] Multi-user support with authentication
- [ ] Key rotation and expiration
- [ ] Rate limiting and abuse prevention
- [ ] End-to-end testing suite

---

## License

MIT

---
