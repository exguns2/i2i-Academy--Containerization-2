# Homework 2: Containerization Project

This repository contains the solution for the **Homework 2 (Containerization)** assignment as part of the i2i Academy program. The objective of this project is to containerize a static web page using Docker and Docker Compose, testing it first in a local environment and then deploying it to a Google Cloud Platform (GCP) Compute Engine virtual machine.

---

## 🚀 Project Overview

The project is structured into two main deployment stages:
1. **Local Deployment:** Running the Nginx container on a local machine (macOS) via Docker Desktop, accessible at `http://localhost:8080`.
2. **Cloud Deployment:** Running the identical setup on a GCP Debian/Ubuntu VM instance, exposed to public HTTP traffic on standard port `80`.

---

## 📁 Repository Structure

* `index.html`: A static HTML file displaying a custom welcome message: *"Hello from i2i Academy Docker Container!"*.
* `docker-compose.yml`: A multi-container orchestration configuration file that defines the Nginx service, port mappings, and volume mounts.

---

## 🛠️ Configuration Details

### 1. Docker Compose Setup
The `docker-compose.yml` file is configured as follows:

```yaml
version: '3.8'

services:
  web:
    image: nginx:latest
    ports:
      - "80:80"  # Configured as 8080:80 for local testing
    volumes:
      - ./index.html:/usr/share/nginx/html/index.html:ro
