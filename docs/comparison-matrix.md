# FitFlow — Weighted Technology Decision Matrix (Activity 3)

Each option is scored 1–10 against weighted criteria reflecting FitFlow's priorities: performance and security are weighted highly due to sensitive health data and real-time UX needs; cost and maintainability reflect the constraints of a mid-sized startup team.

| Option | Performance (20%) | Scalability (15%) | Dev Speed (15%) | Security (15%) | Cost (10%) | AI/ML Support (15%) | Maintainability (10%) | Weighted Total |
|---|---|---|---|---|---|---|---|---|
| React Native (frontend) | 8 | 8 | 9 | 8 | 9 | 8 | 9 | **8.30** |
| Flutter (frontend) | 9 | 8 | 8 | 8 | 8 | 7 | 8 | **8.00** |
| Node.js + Express (backend) | 8 | 8 | 9 | 8 | 9 | 7 | 9 | **8.15** |
| Firebase Firestore + RTDB (database) | 8 | 9 | 9 | 7 | 8 | 7 | 8 | **8.00** |
| PostgreSQL/Supabase (database) | 9 | 7 | 7 | 9 | 8 | 6 | 8 | **7.65** |
| Firebase Auth (authentication) | 8 | 9 | 9 | 8 | 9 | 6 | 9 | **8.20** |

## Recommended Technology Stack

- **Frontend:** React Native (+ React Native Web)
- **Backend:** Node.js + Express
- **Database:** Firebase Firestore + Realtime Database (with optional PostgreSQL/Supabase for relational reporting)
- **Authentication:** Firebase Auth
- **AI/ML:** TensorFlow Lite (on-device) + cloud ML service for heavier models; ML Kit / accessible computer-vision APIs for nutrition photo recognition

This stack scored highest overall on the weighted matrix, aligns with the FitFlow case study's own technology justification, and minimizes integration complexity for a mid-sized team working under time-to-market pressure.
