\<\!-- masterplan.md \--\>  
\# GiftEase App Master Plan

\#\# 1\. App Overview & Objectives    
\- \*\*Overview:\*\* GiftEase simplifies gift-giving for elderly users by letting them manage recipients and events in a simple web dashboard, then receive and act on AI-driven SMS gift reminders.    
\- \*\*Objectives:\*\*    
  1\. Rapidly validate MVP with a small pilot of \~20–50 users    
  2\. Deliver an intuitive, low-friction setup and texting experience    
  3\. Ensure compliance (PCI, GDPR, CCPA) and data security    
  4\. Architect for future scale and richer integrations  

\#\# 2\. Target Audience    
\- Primary: Elderly adults (60+) who want help remembering events and purchasing gifts    
\- Secondary: Tech-savvy children/assistants setting up the dashboard for their parents  

\#\# 3\. Core Features & Functionality    
1\. \*\*Admin Web Dashboard\*\*    
   \- Magic-link login via phone number    
   \- Recipient management: name, age, gender, interests, budget, address    
   \- Event tracking: birthday, anniversary, custom dates    
   \- Payment setup via Stripe Checkout    
2\. \*\*AI-Driven SMS Agent\*\*    
   \- Scheduled reminders (“5 days till John’s birthday…”)    
   \- Inline gift suggestions (Etsy API) with “Reply 1/2/3 to buy”    
   \- Confirmation flows and payment prompts    
   \- Guardrails for clarifications; stops after 1–2 failed attempts    
3\. \*\*Data & Analytics\*\*    
   \- Log sent reminders, replies, purchases    
   \- Simple dashboard metrics (e.g., reminder open rate, conversion)  

\#\# 4\. High-Level Technical Stack    
\- \*\*Frontend:\*\* React (web dashboard) \+ Tailwind CSS    
\- \*\*Backend/API:\*\* Node.js or Python Flask server    
\- \*\*Database:\*\* PostgreSQL (relational, strong schema, ACID)    
\- \*\*SMS Gateway:\*\* Twilio    
\- \*\*E-commerce:\*\* Etsy API (MVP), extend to others later    
\- \*\*Payments:\*\* Stripe Checkout → migrate to Stripe API for dynamic shipping    
\- \*\*AI Agent:\*\* Lightweight GPT-style payloads (via OpenAI API) for templated SMS  

\#\# 5\. Conceptual Data Model    
\- \*\*Users\*\* (admin): id, phone\_number, stripe\_customer\_id    
\- \*\*Recipients\*\*: id, user\_id, name, age, gender, interests, budget, address    
\- \*\*Events\*\*: id, recipient\_id, type, date, last\_reminded\_at    
\- \*\*Gifts\*\*: id, event\_id, suggestion\_data, chosen\_option, purchase\_status    
\- \*\*Logs\*\*: id, user\_id, event\_id, sms\_payload, response, timestamp  

\#\# 6\. UI Design Principles    
\- Minimalist, step-by-step flows (≤5 inputs per step)    
\- High contrast text, large touch targets    
\- Consistent spacing (8–16 px grid), clear affordances    
\- SMS style: friendly, simple sentences; numbered options  

\#\# 7\. Security & Compliance    
\- \*\*PCI:\*\* Use Stripe-hosted checkout for card handling; no card data stored on our servers    
\- \*\*GDPR/CCPA:\*\* Consent on first login; allow data export/deletion    
\- \*\*Encryption:\*\* TLS in transit; AES-256 at rest for sensitive fields  

\#\# 8\. Development Phases & Milestones    
| Phase | Focus                             | Duration | Milestones                              |  
|-------|-----------------------------------|----------|-----------------------------------------|  
| 1     | MVP Setup & Core Flows            | 4 weeks  | Login, recipient/events CRUD, SMS send/receive, basic suggestions  |  
| 2     | Payments & Gift Suggestions       | 3 weeks  | Stripe Checkout integration, Etsy API, purchase confirmation flow  |  
| 3     | Compliance & Analytics            | 2 weeks  | GDPR/CCPA flows, logging, simple dashboard metrics  |  
| 4     | Pilot Launch & Feedback Loop      | 4 weeks  | Onboard 20–50 users, collect feedback, bug fixes  |  
| 5     | Scale & Feature Expansion         | ongoing  | Custom Stripe API, additional retailers, richer UI  |

\#\# 9\. Potential Challenges & Mitigations    
\- \*\*SMS misunderstanding:\*\* implement clarification prompts \+ stop after 2 failed replies    
\- \*\*API rate limits:\*\* cache popular gift lists; graceful degradation    
\- \*\*User onboarding friction:\*\* keep dashboard steps minimal; provide support hotline  

\#\# 10\. Future Expansion Possibilities    
\- Native mobile companion app    
\- Voice reminders (phone calls)    
\- Integration with local retailers, florists    
\- Family-shared dashboards, group gifting  

\#\# 11\. Key documentation  
These documents should be referenced whenever there is core functionality that is being edited:  
\- [implementation-plan.md](http://implementation-plan.md)  
\- [design-guidelines.md](http://design-guidelines.md)  
\- [app-flow.md](http://app-flow.md)  
\- [integrations.md](http://integrations.md) 