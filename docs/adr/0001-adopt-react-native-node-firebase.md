# ADR 0001: Adopt React Native + Node.js/Express + Firebase as the FitFlow redesign stack

**Status:** Accepted

**Context:**
FitFlow needs a fast redesign delivering AI personalization, social features, and nutrition tracking across iOS, Android, and Web, with a mid-sized team and limited time-to-market.

**Decision:**
Use React Native for the client, Node.js/Express for the backend API, and Firebase (Firestore, Realtime Database, Auth, Storage) as the primary data and identity platform, supplemented by TensorFlow Lite and an accessible computer-vision service for AI features.

**Consequences:**
Faster development and lower maintenance cost due to a single JS/TS codebase and reduced vendor count; some vendor lock-in to Firebase; complex relational reporting may require a secondary PostgreSQL store in the future.
