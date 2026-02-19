# 📘 URL Shortener Platform — Full Azure Deployment Guide

A cloud‑native, containerized URL shortener platform built with:

- **Frontend**: Static HTML/JS SPA using MSAL for authentication  
- **Backend API**: Java Spring Boot  
- **QR Generator Microservice**: Python FastAPI  
- **Infrastructure**: Azure Container Apps, Azure Container Registry, Log Analytics, CI/CD, App Registrations  

This guide walks you through setting up the entire system from scratch in Azure.

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

All deployed as Azure Container Apps  
Images stored in Azure Container Registry (ACR)  
Logs collected via Log Analytics Workspace  
CI/CD via GitHub Actions using a Service Principal  
