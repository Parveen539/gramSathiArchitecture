# ADR-0001 : Use Next.js API Routes

## Status  
Accepted  

## Context  
The GramSathi app needs a backend to:
* Handle Authentication (login, signup, JWT)
* Provide CRUD APIs for artisans (poduct, profiles)
* Provide CRUD APIs for farmers (poduct, profiles)
* Provide CRUD APIs for mercants (browse, orders, profiles)
* Support order management

We considered two approaches:  
**1. Use Next.js API Routes** (backend logic in same Nextjs app)  
**2. Use a separate Express.js or Nest.js backend** deploy independently  

## Decision  
We will use Next.js API Routes for the MVP Backend because:  
* It integrare seamlessly with frontend
* Deployment is simple (frontend and backend in one app on Vercel)
* Faster time-to-market with fewer moving part
* Sufficient for handling basic CRUD operation and authentication

## Consequences
### Positive
* Single Codebase -> Frontend + Backend together
* Easy Deployment and scaling via Vercel serverless functions
* Less infrastructure overhead
* Developer Friendly (Shared codebase, easy onboarding)

### Negative
* Limited for long running processes (eg, heavy data processing)
* Backend cannot scale independently of frontend
* Might require migration to a dedicated bacend (Express / Nest.js) if comlexity grows

## Alternatives Considered  
**Express.js** -> More control and flexibility, but require seperate infra setup.  
**Nest.js** -> Enterprise-grade framework, but overkill for MVP  
**AWS Lambda/ Serverless Functions** -> Flexible and scalable, but more setup complexity than needed now.    

This decision will be re-evaluated after MVP Launch depending on traffic, performance and scalability needs.
