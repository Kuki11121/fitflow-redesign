# FitFlow — High-Level Architecture (Activity 4)

See `architecture-diagram.png` in this folder for the full visual diagram.

## Key Components

- **Client layer:** React Native app (iOS/Android) with an offline-first SQLite cache, plus React Native Web sharing the same component codebase.
- **API Gateway:** An Express.js layer exposing REST endpoints and a WebSocket channel for real-time features, and validating Firebase Auth tokens on every request.
- **Core Backend:** Node.js + Express services handling users, workouts, and social interactions, reading/writing to Firestore and the Realtime Database.
- **AI Microservice:** Runs lightweight personalization models on-device via TensorFlow Lite, and calls a cloud ML service for heavier recommendation models.
- **Computer Vision Service:** A dedicated service for camera-based nutrition logging, using an accessible ML kit to recognize food items from photos.
- **Data layer:** Firestore for structured user/workout data, Realtime Database for low-latency social feed and chat, Redis for caching hot data (sessions, active feeds), and Cloud Storage for photos and media.
- **Analytics & Monitoring:** Firebase Analytics and crash reporting feeding the post-deployment monitoring loop described in the case study.

## Data Flows for Critical Features

**Personalized workout plans:** Client requests a plan → API Gateway validates the auth token → Core Backend fetches the user profile from Firestore → AI Microservice generates/refines the plan (on-device model first, cloud model for complex cases) → response cached in Redis and returned to the client.

**Social sharing:** Client posts an update/challenge → Core Backend writes to the Realtime Database → connected clients receive a live push via WebSocket/Firebase listeners → Analytics logs the engagement event.

**Nutrition tracking:** Client captures a food photo → uploaded to Cloud Storage → Computer Vision Service analyzes the image and returns nutrition estimates → Core Backend stores the log entry in Firestore and updates the day's progress dashboard.

## Security, Scalability & Integration Considerations

- **Security:** All traffic over TLS; Firebase Auth issues short-lived JWTs; Firestore/Realtime DB security rules enforce per-user data access; health-related fields encrypted at rest; GDPR/CCPA-compliant data export and deletion endpoints.
- **Scalability:** Firebase services auto-scale; the Express API layer can be horizontally scaled behind a load balancer; Redis absorbs read-heavy traffic (social feed, dashboards) to protect the primary database.
- **Integration:** The AI and Computer Vision services are isolated as separate microservices so they can be scaled, retrained, or replaced independently of the core backend; all inter-service communication goes through the API Gateway or an internal message queue for auditability.
