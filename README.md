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

- [Infrastructure Setup (libply-infra)](libply-infra/README.md)

- [Backend Setup (libply-bk)](libply-bk/README.md)

- [Frontend Setup (libply-ui)](libply-ui/README.md)

### Step 3: Build and Run the Application
After completing the submodule setup:
```bash
cd libply-infra
docker-compose up --build
```
### Step 4: Post-Build Steps

#### Step 1: Create a Superuser
After the first build, create a superuser to access the Django admin panel:
```bash
docker-compose exec backend python manage.py createsuperuser
```

#### Step 2: Configure Admin Panel

Login to Admin Panel
Navigate to https://localhost/admin and log in with your superuser credentials.

#### Step 3: Add a Site

Navigate to `Sites` in the admin panel. 

- Click `Add Site`.

    - Fill out the fields:

        - Domain Name: `localhost:8000`

        - Display Name: `LibPly Local`
    
        - `Save` the site.

#### Step 4: Add Social Applications

Navigate to `Social Applications` in the admin panel.


Click `Add Social Application`. Add an application for Google:
  
  - Provider: `Google`
  - Name: `Google Login`
  - Client ID: `Your Google Client ID`
  - Secret Key: `Your Google Client Secret`
  - Redirect URIs: `https://localhost/api/users/callback/google/`
  - Associate it with the site you created: `(localhost:8000)`

Repeat the process for Spotify:

  - Provider: `Spotify`
  - Name: `Spotify Login`
  - Client ID: `Your Spotify Client ID`
  - Secret Key: `Your Spotify Client Secret`
  - Redirect URIs: `https://localhost/api/users/callback/spotify/`
  - Associate it with the site you created `(localhost:8000)`


### Step 5: Access the Application

https://localhost - signup page
