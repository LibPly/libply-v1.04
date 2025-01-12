# LibPly v1.04

## Overview
LibPly integrates local and cloud music libraries using a modular architecture. This repository serves as the entry point for the application, orchestrating its submodules: frontend, backend, and infrastructure.

## Project Structure

libply-v1.04/

├── libply-ui/        # Frontend (Next.js)

├── libply-bk/        # Backend (Django)

├── libply-infra/     # Infrastructure (Docker Compose, Nginx, SSL)


## Setup Instructions

### Step 1: Clone the Repository
Clone the repository and its submodules:
```bash
git clone --recursive https://github.com/LibPly/libply-v1.04.git
cd libply-v1.04
git submodule update --init --recursive
```

### Step 2: Follow Individual Setup Instructions
Each submodule (libply-ui, libply-bk, libply-infra) has its own README file for setup instructions.

Infrastructure Setup: libply-infra

Backend Setup: libply-bk

Frontend Setup: libply-ui

### Step 3: Build and Run the Application
After completing the submodule setup:
```bash
cd libply-infra
docker-compose up --build
```
### Step 4: Access the Application

Frontend: 

https://localhost/admin - django admin 

https://localhost - signup page
