# HEU-keep

HEU-keep is the **main collaborative repository** for a Keep-style workout card generator adapted for **Harbin Engineering University (HEU)** scenarios.

> **Primary repository:** `lingion/HEU-keep`
>
> This repository is the only mainline source of truth for the project.

## Overview

HEU-keep recreates the visual style of a Keep running summary page and turns it into a configurable web tool. Users can edit workout data, preview the generated result card in real time, draw or generate a running track, and export a high-resolution image.

The project combines:
- a UI-heavy frontend focused on fidelity and export quality
- a Python backend that generates realistic track data
- integration work to connect generated data with the rendered workout card
- collaborative maintenance across frontend, backend, and deployment responsibilities

## Demo-Oriented Highlights

- **High-fidelity UI recreation** of a Keep-style running summary card
- **HEU-specific map adaptation** for local scene realism
- **Real-time preview** while editing workout data
- **Manual track drawing** with Canvas
- **Backend-generated running tracks** with GPS-like drift simulation
- **IndexedDB local persistence** for user settings and assets
- **High-resolution export** through off-screen cloning and html2canvas optimization

## Collaboration Split

### Kerry1020
- frontend optimization
- UI polish and interaction refinement
- mobile adaptation and browser-side testing
- export workflow verification

### Lingion
- backend logic and API design
- Python Flask integration
- deployment and delivery
- full-project integration and engineering packaging

## Tech Stack

### Frontend
- HTML5
- CSS3
- JavaScript (ES6+)
- Canvas
- IndexedDB
- html2canvas

### Backend
- Python 3
- Flask
- Flask-CORS
- NumPy

## Repository Rule

All meaningful project evolution should ultimately land in this repository.
If a collaborator account maintains a presentation copy or mirror, that copy should not replace this repository as the project's mainline.

## Why This Project Matters

This project demonstrates the ability to:
- optimize a visually demanding frontend rather than only build a basic CRUD page
- integrate generated backend data into a highly visual product flow
- solve export-quality and rendering issues in browser-based generators
- maintain a collaborative full-stack project with clear ownership boundaries

## Project Documents

- `ARCHITECTURE.md` — system structure and module responsibilities
- `DEPLOYMENT.md` — how to run frontend and backend
- `RESUME_BULLETS.md` — resume-ready project descriptions
- `TEAM_SPLIT.md` — collaboration role split

## Notes

If another repository under a collaborator account exists, treat it as a collaboration-facing or presentation-oriented copy. The integrated project state belongs here.
