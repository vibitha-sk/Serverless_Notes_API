# Serverless_Notes_API
> Simple Serverless Cloud-Native CRUD API

### 📌 Overview
This project is a demonstration of a fully automated, cloud-native, serverless CRUD API buit on Azure using Azure Functions, Azure Cosmos DB, and Azure Blob Storage.

### 🏗️ Setup Architecture


### 🚀 Features
- Serverless CRUD API — Implements REST-style endpoints using the Azure Functions Python v2 programming model for creating, retrieving, listing, updating, and deleting records.
- Stateless Compute Layer — All the above mentioned operations are handled by a single Function App on a consumption plan — zero idle cost, scales on demand.
- Managed NoSQL Storage — Uses Cosmos DB (SQL API) with a provisioned throughput container, partition key /owner, and UUID-based item IDs.
- Browser-Based Test Client — A simple static website built by HTML demonstrates real-time interaction with the API without requiring additional tooling.
