# OpenPulse Architecture

## Core Components
1. **API Gateway**
   - Entry point for clients
   - Handles REST/WebSocket connections
   - Routes requests to services

2. **Auth Service**
   - Manages users, API keys, JWT
   - Issues and validates tokens

3. **Event Service**
   - Handles event publishing & subscriptions
   - Uses Kafka/Redis for event distribution

4. **Notification Service**
   - Sends push notifications (Web/Mobile)

5. **Database**
   - PostgreSQL for persistence
   - Redis/Kafka for streaming

---

## Data Flow
1. Client authenticates via Auth Service (JWT/API key).
2. Client publishes event → API Gateway → Event Service.
3. Event Service broadcasts event to subscribers via WebSocket or pushes to Notification Service.
4. Notification Service delivers to devices.
