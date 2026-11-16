SellerDoor

Hyperlocal peer-to-peer marketplace with built-in delivery — "Facebook Marketplace meets DoorDash."

Local sellers list items, buyers order them, and a gig driver picks up and delivers — all inside one platform. Designed, built, and tested solo.

Status: In pre-launch testing (iOS & Android). Source code is private; this repo documents the project.

Screenshots
Customer app	Driver app
Customer home	Driver dashboard
Listing detail	Active delivery
What it does
Customer app — browse local listings, place orders, pay in-app, and track delivery in real time.
Driver app — onboarding, accept delivery requests, navigate pickup and drop-off, and cash out earnings.
Seller payouts — sellers and drivers are paid automatically when an order completes.
Architecture
Customer App (Flutter) ─┐
                        ├──► Firebase (Firestore + Auth)
Driver App (Flutter) ───┘          │
                                   ▼
                     Cloud Functions (Node.js)
                       │                   │
                       ▼                   ▼
               Stripe Connect          Mapbox API
         (payments, split payouts,   (maps, routing,
           instant cashouts)        live order tracking)
Tech stack
Layer	Tools
Mobile apps	Flutter, Dart, FlutterFlow
Backend	Firebase Cloud Functions (Node.js), serverless
Database	Cloud Firestore (NoSQL data modeling, security rules)
Auth	Firebase Authentication
Payments	Stripe Connect (split payouts, instant cashouts)
Maps	Mapbox (in-app maps, real-time tracking)
Version control	Git, GitHub
Key engineering work
Two separate apps sharing a single Firebase backend and data model.
Serverless functions that automate order status, driver dispatch, and payout logic.
Stripe Connect integration splitting each payment between the seller, the driver, and the platform.
Real-time order tracking using Mapbox and Firestore listeners.
Driver workflows designed from 5,000+ real-world gig deliveries.
About me

Cameron Pecha — Web Design & Development student at Iowa Western Community College (3.89 GPA), Omaha, NE.

LinkedIn: linkedin.com/in/cameronpecha
Website: sellerdoor.shop
