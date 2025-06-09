```markdown
<!-- integrations.md -->

\# Key Integrations & APIs

| Function               | Service/Platform       | Notes & Alternatives                                  |  
|------------------------|------------------------|-------------------------------------------------------|  
| SMS Gateway            | Twilio                 | Easy SMS \+ magic-link, good docs, pay-as-you-go       |  
| Payment Processing     | Stripe Checkout        | Hosted, PCI-compliant; later migrate to Stripe API    |  
| Gift Catalog           | Etsy API               | Rich marketplace; later add Amazon, local florists    |  
| Backend Hosting        | Heroku / Vercel        | Quick deploy; scale via dynos; alternatives: AWS ECS  |  
| Database               | PostgreSQL (Cloud)     | ACID, relational; alternative: Firebase Firestore     |  
| Scheduling/Jobs        | BullMQ / Redis         | Reliable cron jobs; alternative: AWS EventBridge      |  
| AI Messaging           | OpenAI API             | GPT-style templating; alternative: local LLM, fine-tune|  
| Analytics/Logging      | LogRocket / Datadog    | User logs & metrics; alternative: Grafana \+ Prometheus|

