# My Project

This is a sample project demonstrating the use of Mermaid diagrams within a GitHub `README.md` file.

## Flowchart Example

Below is a simple flowchart illustrating a process.

```mermaid
flowchart TD
  A[User (Browser)] --> B[AAD Login]
  B --> C{JWT Valid?}
  C -->|No| X[Access Denied]
  C -->|Yes| D[IAP passes identity headers]
  D --> E[Fetch role entitlements]
  E --> F[Personalize UI (menus/components)]
  F --> G[Publish JSON (sessionId, action, params)]
  G --> H[Worker validates authorization (RBAC)]
  H --> I[Call Vertex AI / Azure Foundry]
  I --> J[Await completion/callback]
  J --> K[Publish result with sessionId]
  K --> L[Browser filters by sessionId]
  L --> M[Stream tokens (SSE / gRPC-web)]
  J -.-> N[Failure?]
  N --> O[Dead-letter topic]
  O --> P[Alerts & retries (Cloud Functions)]
