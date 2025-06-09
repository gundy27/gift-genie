```markdown
<!-- implementation-plan.md -->

\# Implementation Plan & Scope

\#\# MVP Scope    
\- Web dashboard: magic-link login, recipient & event CRUD    
\- SMS agent: scheduled reminders, gift suggestion messages, reply parsing    
\- Payment: Stripe Checkout for single card on file    
\- Retailer integration: Etsy API for gift options    
\- Logging & basic analytics  

\#\# Development Phases

\#\#\# Phase 1: Core Infrastructure (Week 1–2)    
1\. Set up repo, CI/CD pipeline    
2\. Establish database (PostgreSQL) and ORM    
3\. Implement user model & magic-link SMS login (Twilio \+ JWT)    
4\. Basic dashboard skeleton (React \+ Tailwind)

\#\#\# Phase 2: Recipient & Event Management (Week 3\)    
1\. Recipient CRUD UI & API    
2\. Event CRUD UI & API    
3\. Data validation and error handling

\#\#\# Phase 3: SMS Scheduling & AI Agent (Week 4–5)    
1\. Job scheduler (e.g., cron or queue) for reminder triggers    
2\. SMS template engine with placeholders    
3\. Integrate simple GPT-style calls for dynamic message formatting  

\#\#\# Phase 4: Gift Suggestions & Purchases (Week 6–7)    
1\. Etsy API integration (search and fetch product metadata)    
2\. SMS menu generation with 3 options    
3\. Reply parsing and mapping to product selection    
4\. Stripe Checkout link generation and follow-up SMS

\#\#\# Phase 5: Security, Compliance & Analytics (Week 8\)    
1\. GDPR/CCPA consent flows in dashboard    
2\. Logging service for SMS and purchase events    
3\. Basic metrics dashboard (React charts)

\#\#\# Phase 6: Pilot Launch & Feedback (Week 9–12)    
1\. Deploy to staging → production    
2\. Onboard initial users, collect qualitative feedback    
3\. Rapid bug fixes and UX tweaks  
