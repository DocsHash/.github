# DocHash

Decentralized document verification system through Polygon blockchain

## Project Architecture

DocHash consists of three main components

**Smart Contracts** - Solidity contract for storing SHA-512 document hashes on Polygon blockchain  
**Backend API** - Litestar server with PostgreSQL for file processing and blockchain synchronization  
**Frontend Web** - Svelte application for user interface registration and verification

## System Components

### Blockchain Layer
- Solidity smart contract for Polygon network
- Functions for storing and retrieving document hashes
- Support for localhost, Mumbai testnet, Polygon mainnet
- Unique verification_id for each document

### Backend Service
- Litestar API server with asynchronous architecture
- PostgreSQL database for blockchain data caching
- Web3.py integration for contract interaction
- Blockchain worker for event monitoring
- SHA-512 hashing for contract compatibility

### Frontend Application  
- Svelte web interface with modular architecture
- Drag-and-drop PDF document upload
- Registration and verification interfaces
- Docker containerization with Nginx

## User Scenarios

### Document Registration
1. User uploads PDF file through web interface
2. System generates SHA-512 hash of document
3. Hash is recorded in blockchain contract with unique ID
4. User receives verification_id for future verification

### Document Verification
Document authenticity check through three methods
- By verification_id received during registration
- By original PDF file through re-hashing  
- By known SHA-512 hash of document

### Verification Result
System returns authenticity status with metadata
- Verification status (found/not found in blockchain)
- Blockchain record timestamp
- Creator address
- Transaction details

## Technical Specifications

**Blockchain Networks**
- Polygon Mainnet for production
- Mumbai Testnet for testing  
- Localhost Hardhat for development

**Performance**
- Recording cost around 0.001-0.01 MATIC
- Data reading is free
- Asynchronous API request processing

**Security**
- Cryptographic SHA-512 hashing
- Immutable blockchain records
- Document integrity verification
- Forgery protection through decentralization

## Repository Structure

```
dochash/
├── contracts/          # Solidity contracts and deploy scripts
├── backend/           # API server and blockchain worker  
└── frontend/          # Svelte web application
```

## Quick Start

### Contracts
```bash
cd contracts
npm install && npm run compile
npm run deploy-testnet
```

### Backend  
```bash
cd backend
docker-compose up --build
```

### Frontend
```bash  
cd frontend
yarn && yarn build
docker run -p 80:80 dochash-frontend
```

## Applications

DocHash solves document verification tasks in areas where authenticity is critical
- Legal documentation and contracts
- Academic diplomas and certificates  
- Medical records and prescriptions
- Financial reporting
- Intellectual property
- Government documents

The system provides transparent and immutable recording of document existence at a specific point in time without revealing content
