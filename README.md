# HEU-keep

HEU-keep is a web-based high-fidelity workout record generator tailored for Harbin Engineering University (HEU). It recreates the visual style of Keep running result pages and supports custom workout data, realistic track generation, hand-drawn paths, local persistence, and high-resolution export.

## Project Positioning

This version is packaged as a **backend generation + deployment focused portfolio project**.

### Lingion's Main Contributions
- Backend track-generation logic design
- Python Flask API implementation for realistic running-track generation
- Integration between front-end rendering and backend-generated轨迹 data
- Deployment and runnable delivery setup
- Project-level integration, systemization, and engineering packaging

### Collaboration Split
- **Lingion**: backend logic, deployment, integration, delivery
- **Kerry1020**: frontend optimization, interaction polish, testing and verification

## Key Features
- High-fidelity Keep-style result-card rendering
- HEU map adaptation and multiple scene styles
- Python backend API for track generation
- Randomized ellipse / track simulation with GPS-like drift behavior
- Manual track drawing support on the frontend
- IndexedDB local persistence for user preferences
- High-resolution export through off-screen cloning and html2canvas

## Tech Stack
- HTML / CSS / JavaScript
- Python
- Flask + Flask-CORS
- NumPy
- Canvas / html2canvas
- IndexedDB

## Engineering Highlights
- Designed a backend API for structured track generation (`/generate-track`)
- Combined algorithmic path generation with frontend rendering
- Solved practical export issues with off-screen DOM cloning
- Turned a visually oriented tool into a deliverable, runnable project

## Why This Project Matters
This project demonstrates Lingion's ability to:
- turn a UI tool into a full-stack deliverable
- connect backend-generated data with a highly visual frontend
- package and deploy a niche but concrete product scenario
- describe technical work in terms of architecture, integration, and delivery

## Repository Notes
This repository is presented from the **backend / deployment / integration** perspective.
If you want the frontend / testing focused framing, see the corresponding Kerry-side project packaging.
