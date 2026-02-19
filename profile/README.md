# 📘 URL Shortener Platform — Full Azure Deployment Guide

A cloud‑native, containerized URL shortener-mapping platform built with:

- **Frontend**: Static HTML/JS SPA using MSAL for authentication  
- **Backend API**: Java Spring Boot  
- **QR Generator Microservice**: Python FastAPI  
- **Infrastructure**: Azure Container Apps, Azure Container Registry, Log Analytics, CI/CD, App Registrations  

This guide is produces to deepen my understanding and practical experience/knowledge in the Azure environment in preparation to the AZ-204 exam.
The goal is not to create a flashed out real live application, but to create an ecosystem that incorporates multiple essential Azure Cloud Compute Solutions focusing on DevOps/Deployment aspects.
This guide is written by Stefan Lederhaas.

---

## 🏗️ Architecture overview

```text
┌──────────────────────────┐
│        Frontend SPA      │
│  (HTML/JS + MSAL Auth)   │
└──────────────┬───────────┘
               │
               ▼
┌──────────────────────────┐
│     Spring Boot API      │
│       (Shortener)        │
└──────────────┬───────────┘
               │
               ▼
┌──────────────────────────┐
│   FastAPI QR Generator   │
└──────────────────────────┘
```

All deployed as Azure Container Apps  
Images stored in Azure Container Registry (ACR)  
Logs collected via Log Analytics Workspace  
CI/CD via GitHub Actions  

##  Prerequisites
- Azure subscription (I used a student subscription with free 100$ credits)
- Azure CLI installed or using the Azure browser cloud shell
- Docker doesn't need to be installed!
- Git repos for the different apps
