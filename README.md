# Serverless_Notes_API
> Simple Serverless multi-user Cloud-Native CRUD API

### 📌 Overview
This project is a demonstration of a fully automated, cloud-native, serverless CRUD API buit on Azure using Azure Functions, Azure Cosmos DB, and Azure Blob Storage. It supports multi-user data isolation and is secured with Microsoft Entra ID.

### 🏗️ Setup Architecture
![setup](images/Architecture_Diagram.png)


### 🚀 Features
- Serverless CRUD API — Implements REST-style endpoints using the Azure Functions Python v2 programming model for creating, retrieving, listing, updating, and deleting records.

- Authenticated REST Endpoints  — All REST endpoints require a valid Entra External ID access token. The function code validates the JWT signature against the Entra JWKS endpoint and rejects unsigned or expired tokens with HTTP 401.

- Per-User Data Isolation — The Cosmos DB partition key /owner is set from the JWT sub claim. Each user can only read and write their own notes — enforced at the storage layer, not just the application layer.

- PKCE OAuth2 Flow — The SPA utilizes the Authorization Code Flow with PKCE for secure, secretless authentication in the browser. The authentication callback exchanges the auth code for access tokens and manages session state via sessionStorage for clean logouts.

- Stateless Compute Layer — All the above mentioned operations are handled by a single Function App on a consumption plan — zero idle cost, scales on demand.

- Managed NoSQL Storage — Uses Cosmos DB (SQL API) with a provisioned throughput container, partition key /owner, and UUID-based item IDs.

- Browser-Based Test Client — A simple static website built by HTML demonstrates real-time interaction with the API without requiring additional tooling.
