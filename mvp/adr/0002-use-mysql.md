# ADR-0002: Use MySQL as Primary Database 

## Status
Accepted

## Context
The GramSathi App requires a database to store:  
* User Profiles (artisans, farmers, merchants, admin).  
* Product Listing (name, price, category, stock).  
* Orders (merchants, farmer, artisans, status, timestamps).

We considered three main options:  
**1. MySQL** -> Relational, widely supported, good for hosting options.  
**2. PostgreSQL** -> Advanced relational features, powerful but slighty heavier.  
**3. MongoDB** -> Flexible Schema, great for unstructured data.  

## Decision 
We will use MySQL as primary database for MVP because:  
* Well suited for relational data like users, product, orders  
* Developer on team already have MySQL Expertise  
* Hosting options are cheap and widely available (e.g. PlanetScale, Railway, AWS RDS)  
* The schema is relatively stable and don't require NoSQL flexibility  
* Simpler to integrate with Next.js routes via popular ORMs (Prisma, Sequelize)

## Consequences
### Positive
* Familiar and proven technology for structured data.
* Easy onboarding for developers.
* Mature ecosystem, drivers, ORM Support.
* Scales well enough for MVP and beyond.

### Negative 
* Less flexible for schema changes compared to NoSQL.
* May require Migration to PostgreSQL or sharding if very large scale is reached.
* Slghtly less feature-rich than PostgreSQL (e.g. JSONB, advance indexing).

## Alternatives Considered  
**PostgreSQL** -> More features, but not necessary at MVP stage. Could be adopted later if required.  
**MongoDB** -> Provides schema flexibility, but would complicate queries and relationships (users → products → orders).  
**SQLite** -> Lightweight, but not scalable for production.  

Decision will be revisited if data relationships become too complex or scaling requirements exceed MySQL's capabilities.
