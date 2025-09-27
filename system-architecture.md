# 1. Introduction
This document carries System Architecture for gramSathi Application. gramSathi is applcation for making life easier for people of villages. This application connect Farmers and Artisans in villages to connect with merchants for selling their produce. Application reduce the involvement of middlemen hence empower artisans, farmers and mercants to get fair price and fresh produce.

**Links to:** [Vision and Requirements](https://github.com/Parveen539/gramSathiArchitecture/blob/main/vision-and-requirements.md)

# 2. System Context
- Artisan
- Farmers
- Merchant
- Admins

Artisans --> GramSathi App  
Farmers --> GramSathi App  
Merchants --> GramSathi App  
Admins --> GramSathi App  
GramSathi App --> GramSathi Backend  
GramSathi App --> Weather API  
GramSathi Backend --> Database  

# 3. Architecture Overview
## Architecture style:
- modular monolith
  
## Technology stack:
**Frontend:** Next.js  
**Backend :** Node.js  
**Database :** MySql  
**Auth :** JWT  
**Hosting:** Vercel  

# 4. Module/ Component View
**Home Module:** weather information  
**Auth Module:** login, signup, JWT, validation  
**Artisan Module:** profile, product  
**Farmer Module:** profile, product  
**Merchant Module:** profile, browse, order  
**Order Module:** order placement, tracking  

# 5. Data Model
**Tables:** user, product, order  
**Relationships:** N:M Farmer -> Product;  N:M Artisan -> Product;  N:M Merchant -> Order 

# 6. Deployement View
**Frontend:** Vercel  
**Backend:** AWS  
**DB:** PlanetScale MySql  
**File storage:** S3  

# 7. Cross-Cutting Concerns
**Security:** HTTPS, JWT, password hashing  
**Logging/ Monitoring:** Basic request logging, error tracking  
**Scalabilty:** auto-scaling via Vercel  
**DevOps:** CI/CD pipeline (GitHub Actions -> deploy to vercel / AWS)  

# 8. Architecture Decisions
Please Refer to following:
[Use nextjs api routes](https://github.com/Parveen539/gramSathiArchitecture/blob/main/adr/0001-use-nextjs-api-routes.md)

# 9. Risks & Mitigations
**Risk:** Poor internet in rural areas -> **Mitigation:** Optimize for mobile caching  
**Rist:** Artisan/ Farmers unfamiliar with tech -> **Mitigation:** Very simple UX, Large Fonts  

# 10. Roadmap (Architecture Evolution) 
**Phase 1:** (MVP): Modular Monolith in Next.js + MySql  
