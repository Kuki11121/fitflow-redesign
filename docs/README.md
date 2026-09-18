# FitFlow Redesign

## Project Overview

FitFlow is a fitness tracking application redesign based on a human-centered design case study. The redesign addresses the following key problems and introduces features to solve them:

- **Personalization gap** — Addressed through AI-powered personalized workout plans.
- **Social isolation** — Addressed through social community features.
- **High friction in daily tracking** — Reduced through streamlined tracking features.
- **Lack of motivation/celebratory elements** — Addressed through engaging progress dashboards and social features.
- **Nutrition tracking friction** — Improved through computer vision for nutrition photo recognition.

## Project Objectives

The primary objective of the redesign is to create a more engaging, personalized, and socially connected fitness tracking experience that reduces user friction and increases long-term motivation.

## Selected Technology Stack

| Component | Technology | Purpose |
|---|---|---|
| Frontend | React Native | Cross-platform mobile application (iOS/Android) |
| Web | React Native Web | Web compatibility using the same codebase |
| Backend | Node.js + Express.js | Core API and backend services |
| Database | Firebase Firestore + Realtime Database | Primary NoSQL datastore and real-time social features |
| Authentication | Firebase Authentication | Secure user identity and sign-in management |
| AI/ML | TensorFlow Lite + Cloud ML | On-device personalization and heavier recommendation models |
| Computer Vision | ML Kit / accessible computer-vision service | Nutrition photo recognition |
| Cache | Redis | Server-side caching for performance |
| Storage | Firebase Cloud Storage | Storing user media and application assets |
| Analytics | Firebase Analytics & Crash reporting | User behavior tracking and application stability monitoring |
| Client-side offline cache | SQLite | Offline data support |

> **Note:** PostgreSQL/Supabase may be used optionally as a secondary database for relational reporting needs.

## Architecture Overview

The system utilizes a modern, decoupled architecture with a React Native client communicating through an Express API Gateway to backend microservices, including specialized AI and Computer Vision components.

For full details, please see the [High-Level Architecture documentation](docs/architecture.md).

## Repository Structure

```
fitflow-redesign/
├── README.md
├── .gitignore
├── frontend/
├── backend/
├── ai-service/
├── docs/
│   ├── technology-comparison.md
│   ├── decision-matrix.md
│   ├── architecture.md
│   ├── ADR.md
│   └── architecture-diagram.png
└── docs/report/
    └── README.md
```

## Key Features

- AI personalized workout plans
- Social community/challenges
- Nutrition tracking using camera/computer vision
- Progress dashboard
- Real-time notifications/social interactions
- Offline support

## Documentation

- [Technology Comparison](docs/technology-comparison.md)
- [Weighted Decision Matrix](docs/decision-matrix.md)
- [High-Level Architecture](docs/architecture.md)
- [Architecture Decision Record](docs/ADR.md)
- [Architecture Diagram](docs/architecture-diagram.png)

## Academic Context

IT3060 – Human Computer Interaction, Lab Exercise 05
BSc (Hons) Information Technology
