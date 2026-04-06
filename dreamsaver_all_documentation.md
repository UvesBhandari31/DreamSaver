# DreamSaver

## Project Description
A web application that allows users to track their dreams and gain meaningful insights using AI. The app will use Gemini AI to analyze dreams and provide interpretations. The overall design should have a dreamy, aesthetic feel.

The application will include a landing page that introduces the project and features a text box where users can submit their first dream. Submitting a dream will automatically sign the user up and store their entry.

Users will have access to a dashboard that displays all their recorded dreams. When a user selects a specific dream, they will be taken to a detailed page showing the dream content, related metadata, and AI-generated insights.

In the free tier, users can record an unlimited number of dreams, but they will receive only 5 AI-generated insights. A paid subscription plan will be available at ₹299 per month, allowing users to access unlimited AI insights.


## Product Requirements Document
PRODUCT REQUIREMENTS DOCUMENT (PRD) - DreamSaver

1. Introduction and Goals

1.1 Project Overview
DreamSaver is a web application designed to help users log, analyze, and gain meaningful insights from their dreams. Leveraging the Gemini AI model, the application will provide multi-faceted interpretations of user-submitted dream narratives, presented in an aesthetically pleasing, calming, and dreamy interface. The initial launch (MVP) will focus on core logging, AI analysis (limited for free users), and user dashboard functionality.

1.2 Goals
1. Provide a secure and intuitive platform for dream journaling.
2. Utilize Gemini AI to deliver structured, multi-dimensional analysis of dream content.
3. Establish a clear, aesthetically pleasing, and immersive user experience (dreamy/calming aesthetic).
4. Implement a functional freemium model clearly outlining usage limits and subscription benefits.
5. Launch a stable MVP within a 3–4 week timeline using only free-tier infrastructure.

1.3 Target Audience
The primary audience consists of individuals aged 16–35, including students, young professionals, and creative individuals (writers, artists) interested in self-growth, mental wellness, and pattern recognition in their subconscious experiences. They expect personalized, meaningful AI feedback linking dreams to real life.

2. Features and Requirements

2.1 Landing Page (Public & Onboarding)
REQ-LP-001: The landing page must introduce DreamSaver, highlighting the AI analysis capabilities and the aesthetic design.
REQ-LP-002: Must prominently feature a text input area (Dream Submission Widget).
REQ-LP-003: Submitting a dream via this widget must automatically initiate user registration/login flow (if not already logged in) and store the entry.

2.2 User Authentication and Data Security
REQ-SEC-001: Implement secure user registration and login mechanisms (e.g., OAuth or secure password hashing).
REQ-SEC-002: All user data, especially dream content and metadata, must be encrypted both in transit (TLS/SSL) and at rest.
REQ-SEC-003: Users must have explicit controls to edit or completely delete their submitted dream entries and associated data.
REQ-SEC-004: Privacy policy must clearly disclose the use of Gemini AI for analysis and how the input data is processed (data minimization principle).

2.3 Dream Submission & Metadata Capture
REQ-SUB-001: Users must be able to submit the main text body of the dream.
REQ-SUB-002: A title field for the dream entry is mandatory.
REQ-SUB-003: Users must record the following basic metadata: Date/Time of Sleep, Wake-up Time, and Estimated Sleep Duration.
REQ-SUB-004: Users must be able to tag the dream with one or more emotional tones (e.g., Happy, Anxious, Scary, Confusing).
REQ-SUB-005: Users must be able to select noticeable themes (e.g., Falling, Chased, Flying).
REQ-SUB-006: Users must be able to rate the Clarity/Vividness of the dream (e.g., 1–5 scale).
REQ-SUB-007: Optional contextual fields required for enhanced AI analysis: Stress Level before sleep, Mood before bed, Unusual pre-sleep activities (text input/checkboxes), and a flag indicating if it felt like a Recurring Dream.
REQ-SUB-008: Users must be able to mark if the dream felt Realistic or Surreal.

2.4 Dream Dashboard
REQ-DASH-001: The dashboard must display a list of all previously recorded dreams.
REQ-DASH-002: Each list item must clearly show: Date, a short snippet (first 50 characters) of the dream content, associated emotional tags, and a visual indicator of whether AI insights are available for that entry.
REQ-DASH-003: The dashboard must support basic filtering options (Filter by Theme, Filter by Emotion).
REQ-DASH-004: The dashboard must support sorting options (Sort by Date Asc/Desc, Sort by Last Activity).
REQ-DASH-005: The dashboard must clearly display the user's current plan status (Free or Paid) and the remaining count of available free AI insights.

2.5 Detailed Dream View & AI Insights
REQ-DETAIL-001: Navigating to a specific dream must display the full dream text, all submitted metadata, and the date/time of entry.
REQ-DETAIL-002: AI insights will only be generated/displayed if the user has remaining insights or a paid subscription.
REQ-DETAIL-003: The AI analysis must generate the following distinct insight types:
    a) Symbolic Analysis (Interpretation of common dream elements).
    b) Psychological Connections (Linking dream content to potential real-life stress/thoughts).
    c) Recurring Motif Identification (Highlighting detected patterns across the user’s dream history).
    d) Emotional Summary (Highlighting dominant feelings).
    e) Trend Insights (Brief overview of how this dream fits into recent patterns).
    f) Creative Interpretations (Potential ideas or inspiration derived from the dream).
REQ-DETAIL-004: **Structured Presentation:** Insights must be presented in clearly separated sections, not as a single block of text.
    a) Symbolic Analysis: Displayed as distinct bullet points or small summary cards for each symbol.
    b) Emotional Summary: Presented as quick tags or highlights.
    c) Recurring Motifs: Displayed as actionable links pointing to previous, similar dream entries.
    d) Psychological Insights: Presented in a slightly more detailed, conversational paragraph format.
    e) Trend Insights: Summarized briefly, potentially using simple visual cues if applicable within MVP scope.

2.6 AI Integration (Gemini) Constraints
REQ-AI-001: Prompt engineering must prioritize conciseness to manage latency, adhering strictly to Gemini API token limits where possible.
REQ-AI-002: For complex analyses requiring multiple perspectives (as outlined in REQ-DETAIL-003), prompt chaining or multi-step analysis should be planned conceptually, even if MVP focuses on simpler, aggregated prompts to maintain budget/speed.

3. Monetization and Subscription Management

3.1 Freemium Model Enforcement
REQ-SUB-001: Free Tier: Unlimited dream logging, but strictly limited to 5 total AI-generated insights across the lifetime of the account.
REQ-SUB-002: Paid Tier (₹299/month): Unlimited AI-generated insights.
REQ-SUB-003: The system must accurately track the count of insights consumed against the free limit.

3.2 Subscription Flow
REQ-SUB-004: A clear Call-to-Action (CTA) must be present on the dashboard and detailed dream view when insights are exhausted, prompting users to upgrade.
REQ-SUB-005: The upgrade flow must integrate a reliable payment gateway supporting standard methods (Cards, UPI).
REQ-SUB-006: Users must have a dedicated Subscription Management section.
REQ-SUB-007: Subscription Management must clearly show: Current Plan, Billing Cycle Start/End Date, and Next Renewal Date.
REQ-SUB-008: Users must have the ability to cancel their subscription at any time, which should take effect at the end of the current billing cycle.
REQ-SUB-009: Users should receive pre-renewal notifications (e.g., 3 days prior to charge).

4. Technical & Design Specifications

4.1 Technical Stack (MVP Focus)
REQ-TECH-001: The MVP must be built exclusively using free tiers of relevant services:
    a) Hosting: Vercel or Netlify (Free Tier).
    b) Database: Firebase (Free Tier) or Supabase (Free Tier).
    c) AI Processing: Gemini API (Leveraging initial free credits).
    d) Payment Gateway: Integration must use a service offering a suitable free/low-cost entry point for subscription handling (e.g., Stripe integration configured for minimal overhead).

4.2 Design Aesthetic
REQ-DESIGN-001: The application must adopt a dreamy, calming aesthetic using soft, minimal UI elements.
REQ-DESIGN-002: Primary color palette should favor dark mode: deep blues, violets, and subtle gradients to evoke a night/celestial feel.
REQ-DESIGN-003: UI elements should incorporate visual effects such as soft blurs, gentle shadows, and smooth, unobtrusive animations/transitions to enhance the surreal, immersive mood.
REQ-DESIGN-004: Overly bright or jarring colors and cluttered layouts are strictly prohibited.

5. Timeline and Budget (MVP)
REQ-TIME-001: The targeted timeline for MVP launch is 3–4 weeks.
REQ-TIME-002: The budget allocation for the MVP phase is ₹0, relying strictly on free tiers and initial credits. Resource management must prioritize stability and core feature delivery over complex optimizations or premium integrations.

6. Future Considerations (Post-MVP)
(Note: These are documented for completeness but are explicitly out of scope for the initial 3-4 week MVP delivery.)
F-001: Advanced trend visualization (charts comparing mood/themes over months).
F-002: Community features or sharing of non-private insights.
F-003: Integration with wearable devices for sleep tracking data import.
F-004: Exploration of advanced AI prompting techniques (e.g., chain-of-thought) once token usage/latency is better understood post-launch.

## Technology Stack
# DreamSaver Technology Stack (TechStack Document)

## 1. Overview and Design Philosophy

The technology stack for DreamSaver is chosen to prioritize rapid MVP development (3-4 weeks), cost-effectiveness (₹0 budget using free tiers), and the delivery of a highly aesthetic, responsive user experience. Given the reliance on Gemini AI for core functionality and the need for robust user management and data handling, the stack balances modern development practices with accessibility to free resources. The aesthetic goal—dreamy, calming, dark mode focus—heavily influences frontend choices.

## 2. Frontend (Client-Side)

The frontend must deliver a fast, responsive interface with subtle, atmospheric visual effects suitable for the aesthetic requirements.

| Technology | Purpose | Justification |
| :--- | :--- | :--- |
| **React (Vite/Next.js)** | Core UI Framework | Provides component-based architecture for building complex interfaces. Vite offers blazing-fast development server speeds, ideal for rapid MVP iteration. Next.js (if server-side rendering or routing complexity increases) offers excellent structure, but Vite is prioritized for the initial free-tier MVP timeline. |
| **TypeScript** | Language | Enhances code quality, maintainability, and reduces runtime errors, especially when handling complex metadata structures for dreams and AI responses. |
| **Tailwind CSS / PostCSS** | Styling Utility | Enables rapid styling development. Critical for achieving the specified dark mode, gradient, and soft/minimal aesthetic without writing extensive custom CSS files. Utility-first approach speeds up theme implementation. |
| **Framer Motion** | Animation Library | Essential for implementing the "smooth animations" and "gentle transitions" required for the dreamy aesthetic, enhancing immersion without complex custom JavaScript animation logic. |
| **Zod or Yup** | Schema Validation | Used for validating user input (dream submission metadata) before sending data to the backend or processing locally. |

## 3. Backend (Server-Side / API Layer)

The backend needs to manage user authentication, secure dream storage, handle subscription state, and act as the secure intermediary with the Gemini API. Given the MVP budget constraint, a serverless approach using free tiers is mandated.

| Technology | Purpose | Justification |
| :--- | :--- | :--- |
| **Node.js (Express or Serverless Functions)** | API Runtime Environment | Standard, versatile platform for building RESTful APIs. Serverless functions (e.g., on Vercel or Netlify) fit the initial ₹0 budget model perfectly, scaling compute usage only when requests are made. |
| **NextAuth.js (If using Next.js) or Passport.js (If pure Express)** | Authentication | Provides secure, standardized methods for user sign-up/login, crucial for meeting data security requirements (secure login). Works well with credential providers for basic email/password or social logins if needed later. |
| **Prisma (or similar ORM)** | Database Access Layer | Provides a modern, type-safe way to interact with the chosen database. Simplifies migrations and query construction. |

## 4. Database and Data Management

Data storage must be secure, reliable, and offer a generous free tier to accommodate unlimited dream entries for free users.

| Technology | Purpose | Justification |
| :--- | :--- | :--- |
| **Supabase or Firebase (Firestore)** | Primary Database | Both offer robust, scalable solutions with extremely generous free tiers suitable for an MVP. Supabase (PostgreSQL based) offers strong relational integrity, while Firestore (NoSQL) offers flexibility, which might suit unstructured dream text better initially. **Recommendation: Supabase** for its strong security features and integrated authentication hooks, aligning with data security goals. |
| **Encryption at Rest/Transit** | Security | While the database layer handles much of this, ensure all API communication uses HTTPS/SSL (standard with modern hosting platforms). Sensitive user data in the database schema should be handled with awareness of platform security features. |

## 5. AI Integration (Gemini)

The core value proposition relies on high-quality, structured AI insights derived from Gemini.

| Technology | Purpose | Justification |
| :--- | :--- | :--- |
| **Google Gemini API (Pro or Flash Model)** | Core AI Analysis Engine | Directly addresses the project requirement to use Gemini for dream interpretation. The API key will be strictly secured on the backend server, never exposed client-side. |
| **Prompt Engineering & Chaining** | Insight Generation Logic | Essential for meeting the requirement for *multiple, structured insight types* (Symbolic, Psychological, Emotional, etc.). Prompts must be carefully designed to demand structured JSON or specific formatting to ensure easy parsing and presentation on the detailed dream page, helping manage Gemini API constraints (latency/tokens). |
| **Token Management Strategy** | Constraint Handling | Implement logic to keep initial prompts concise. For deeper analysis, employ prompt chaining where the initial dream summary is fed into subsequent, specialized prompts, optimizing token usage and adhering to latency concerns. |

## 6. Infrastructure and Deployment (MVP Focus)

Infrastructure must be zero-cost for the initial phase.

| Technology | Purpose | Justification |
| :--- | :--- | :--- |
| **Vercel or Netlify** | Frontend & Serverless Hosting | Both offer excellent integration with React/Next.js and provide generous free tiers suitable for hosting the frontend application and the associated serverless backend functions (API routes). Vercel is often slightly favored for Next.js deployments. |
| **GitHub Actions / GitLab CI** | CI/CD | Basic Continuous Integration setup for automated testing and deployment to the chosen host upon merging to the main branch. |

## 7. Subscription and Payment Management

A reliable, low-overhead system is needed for managing the ₹299/month subscription.

| Technology | Purpose | Justification |
| :--- | :--- | :--- |
| **Stripe** | Payment Gateway | Industry standard, robust, and offers excellent documentation and SDKs. Crucial for handling card/UPI payments and managing recurring subscriptions (managing plan status, renewal dates, billing history). |
| **Backend Logic (Webhooks)** | Subscription State Sync | Backend must listen for Stripe webhooks (e.g., `invoice.paid`, `customer.subscription.deleted`) to accurately update the user's `plan_status` in the primary database (Supabase/Firebase). |

## 8. Data Structure Considerations (Influencing Tech Choice)

The required metadata capture necessitates a flexible yet structured data model:

*   **Dream Entry:** Title, Content (Text), Timestamp (Sleep Start/End), Duration.
*   **Metadata Tags (User Input):** Emotional Tags (Array), Theme Tags (Array), Clarity Rating (Number), Stress Level (Number), Realism (Boolean).
*   **AI Insights:** JSON object containing segregated fields for each insight type (e.g., `symbolic_analysis: [...]`, `psychological_connections: "..."`). This structured storage is vital for the required segmented display on the detailed page.
*   **User Management:** Plan Status (Free/Paid), AI Insights Remaining (Integer). This must be easily queryable by the backend when processing new insight requests.

## Project Structure
PROJECT STRUCTURE DOCUMENT: DREAMSAVER

1. PROJECT OVERVIEW
====================
Project Name: DreamSaver
Description: A web application utilizing Gemini AI for dream journaling, analysis, and insight generation, featuring a calming, aesthetic design suitable for wellness tracking.

2. HIGH-LEVEL DIRECTORY STRUCTURE
=================================
/dream-saver
├── .github/              # CI/CD pipelines, issue templates (if applicable)
├── .husky/               # Git hooks configuration
├── .vscode/              # VS Code specific settings (optional)
├── node_modules/         # Project dependencies
├── public/               # Static assets (images, fonts, favicon)
├── src/                  # Application source code (Frontend & Backend logic)
├── tests/                # Unit and integration tests
├── .env                  # Environment variables (DB credentials, API keys)
├── .gitignore
├── package.json          # Project dependencies and scripts
├── tsconfig.json         # TypeScript configuration
└── README.md             # Project documentation entry point

3. DETAILED SOURCE DIRECTORY STRUCTURE (/src)
============================================
The application will likely adopt a monorepo or tightly coupled structure suitable for a 3-4 week MVP, potentially using Next.js or a similar framework that combines frontend and API routes.

/src
├── api/                  # Backend API endpoints (Serverless functions/API routes)
│   ├── auth/             # Authentication handlers (Signup, Login, Session management)
│   ├── dreams/           # Dream management CRUD operations
│   ├── insights/         # Handlers for calling Gemini AI and processing results
│   └── subscription/     # Payment gateway integration handlers (e.g., Razorpay webhook setup)
│
├── components/           # Reusable UI components (React/Vue components)
│   ├── common/           # Generic components (Button, Input, Modal)
│   ├── layout/           # Structural components (Header, Footer, Navigation)
│   ├── dashboard/        # Components specific to the dashboard view
│   └── insights/         # Components for rendering specific AI insight types
│
├── config/               # Configuration files
│   ├── index.ts          # Global configuration setup
│   └── gemini.ts         # Gemini API initialization and base prompt settings
│
├── constants/            # Static configuration values (e.g., subscription tiers)
│   ├── index.ts
│   └── tiers.ts          # Defines FREE_TIER_INSIGHTS_LIMIT (5) and PAID_TIER_PRICE (299)
│
├── lib/                  # Utility functions and external service wrappers
│   ├── db.ts             # Database connection/ORM setup (e.g., Firebase/Supabase client)
│   ├── encryption.ts     # Utilities for data security (encryption/hashing)
│   ├── geminiService.ts  # Wrapper around Gemini SDK, handles prompt construction and constraints
│   └── payment.ts        # Abstraction layer for the payment gateway integration
│
├── hooks/                # Custom frontend hooks (e.g., useSubscriptionStatus)
│   └── useSubscription.ts
│
├── models/               # Data schemas and TypeScript interfaces
│   ├── Dream.ts          # Interface for Dream submission data (including metadata)
│   ├── User.ts           # User profile structure
│   └── Subscription.ts   # Plan status and billing details
│
├── pages/                # Application views/routes (if using Next.js)
│   ├── api/              # (If not using /src/api directly, common in Next.js)
│   ├── _app.tsx          # Global wrapper/context provider
│   ├── index.tsx         # Landing Page
│   ├── dashboard.tsx     # User Dashboard
│   ├── dream/[id].tsx    # Detailed Dream View Page
│   └── settings.tsx      # Account/Subscription Management Page
│
└── styles/               # Global styling (CSS Modules, Tailwind config, custom aesthetics)
    ├── globals.css       # Base styles, font imports
    └── theme.css         # Defines dreamy palette (deep blues, purples, soft gradients)

4. DATA MODEL STRUCTURE (Conceptual - defined in /models)
=========================================================
4.1. Dream Model (dream.ts)
---------------------------
- id: string
- userId: string
- title: string
- content: string (Full dream text)
- submissionTimestamp: Date
- metadata: {
    sleepDate: Date,
    wokeUpTime: string,
    durationMinutes: number,
    emotionalTone: string[], // Tags: happy, anxious, etc.
    themes: string[],       // Tags: falling, flying, etc.
    clarityRating: number,  // 1-5
    vividnessRating: number, // 1-5
    isRecurring: boolean,
    realism: 'realistic' | 'surreal',
    preSleepFactors: { stressLevel: number, moodBeforeBed: string, lateNightActivity: string }
}
- insightsGenerated: boolean
- insights: {
    type: 'symbolic' | 'psychological' | 'recurring' | 'emotional' | 'trend' | 'creative',
    content: string, // The AI-generated text for this specific insight type
    status: 'pending' | 'complete'
}[]

4.2. User Model (user.ts)
-------------------------
- id: string
- email: string
- plan: 'free' | 'paid'
- aiInsightsUsedCount: number (Reset monthly or based on logic)
- subscriptionDetails: {
    startDate: Date,
    nextBillingDate: Date,
    paymentGatewayId: string
}

5. AI INSIGHT MAPPING & PRESENTATION STRATEGY (Referenced in /components/insights)
===================================================================================
The structure in the Dream Model allows for the detailed presentation required on the dream detail page:

| Insight Type | Presentation Method | Notes |
|---|---|---|
| Symbolic Analysis | Short, itemized list of symbols and meanings. | Direct mapping of symbols found in content. |
| Emotional Summary | Quick highlight tags or a dominant color/mood representation. | Based on user tag and AI inference. |
| Psychological Connections | Conversational, slightly longer paragraph format. | Linking dream content to potential waking life stressors. |
| Recurring Motif Identification | Links/references to past dreams matching themes. | Requires historical analysis query. |
| Trend Insights | Brief summary or small visualization snippet. | Compares recent dream patterns vs. historical average. |
| Creative Interpretations | Inspirational sentence or short idea prompt. | Focus on artistic application for the target audience. |

6. SECURITY AND PRIVACY STRUCTURE (/lib, /api/auth)
====================================================
- **Data Encryption:** All sensitive PII and dream content stored in the database must use field-level or database-level encryption (handled by `lib/encryption.ts` and DB setup).
- **Secure Login:** Implementation via JWT or Session management handled in `/api/auth`.
- **Data Minimization:** Only collect metadata strictly necessary for personalization (as defined in Dream Model).
- **Access Control:** Strict authorization checks on all dream retrieval endpoints (`/api/dreams`).

7. SUBSCRIPTION MANAGEMENT FLOW (/api/subscription, /pages/settings.tsx)
========================================================================
- **Free Tier Tracking:** `/lib/geminiService.ts` checks `User.aiInsightsUsedCount` against `constants.tiers.FREE_TIER_INSIGHTS_LIMIT` before generating AI analysis.
- **Upgrade Path:** Accessible via `/settings.tsx`, triggers payment gateway initiation via `/api/subscription/initiatePayment`.
- **Webhook Handling:** Secure endpoint `/api/subscription/webhook` to handle payment success/failure notifications from the gateway, updating the `User.plan` status.

## Database Schema Design
SCHEMADESIGN - DreamSaver Database Schema

1. OVERVIEW AND DESIGN PHILOSOPHY

The database schema for DreamSaver is designed to be secure, scalable (within MVP constraints), and optimized for efficient retrieval of dream content and associated AI insights. Given the MVP budget constraint (₹0, free tiers), the schema prioritizes simplicity and direct mapping to core application features.

Aesthetic Consideration: While the database structure itself is functional, field naming conventions will prioritize clarity (e.g., `user_id` instead of overly cryptic aliases) to support future development where aesthetic presentation relies on the structured data retrieved.

2. ENTITIES AND RELATIONSHIPS

The core structure involves three main entities: Users, Dreams, and AI Insights. Relationships are primarily one-to-many (User to Dreams, Dream to Insights).

3. DATA MODELS (TABLE STRUCTURES)

We assume a relational database structure (e.g., PostgreSQL via Supabase/Vercel Postgres, or Firestore equivalent structure).

---

### Table 1: Users

Stores user authentication and subscription data. Data privacy (encryption) must be enforced at the application/infrastructure layer for sensitive fields like `password_hash` and `email`.

| Field Name | Data Type | Constraints / Notes | Purpose |
|---|---|---|---|
| `user_id` | UUID/Serial | Primary Key | Unique identifier for the user. |
| `email` | String | Unique, Not Null | User login identifier. |
| `password_hash` | String | Not Null | Securely hashed password. |
| `created_at` | Timestamp | Not Null, Default Current Time | Record creation timestamp. |
| `plan_status` | Enum (FREE, PAID) | Not Null, Default FREE | Current subscription status. |
| `ai_insights_used` | Integer | Not Null, Default 0 | Counter for insights consumed in the current billing cycle (reset upon renewal/upgrade). |
| `subscription_end_date` | Timestamp | Nullable | Date when the paid subscription expires (if applicable). |
| `payment_gateway_id` | String | Nullable | Reference ID from the payment processor for billing management. |

---

### Table 2: Dreams

Stores the primary dream journal entries and associated metadata capture during submission.

| Field Name | Data Type | Constraints / Notes | Purpose |
|---|---|---|---|
| `dream_id` | UUID/Serial | Primary Key | Unique identifier for the dream entry. |
| `user_id` | Foreign Key | Not Null, References Users(`user_id`) | Links the dream to the owner. |
| `title` | String (Max 100 chars) | Optional | User-provided title for the dream. |
| `dream_content` | Text | Not Null | The full, detailed text of the dream. |
| `submission_timestamp` | Timestamp | Not Null | When the user logged the dream. |
| `sleep_duration_minutes` | Integer | Nullable | How long the user slept (metadata). |
| `clarity_rating` | Integer (1-5) | Nullable | User rating of dream vividness/clarity. |
| `realism_type` | Enum (REALISTIC, SURREAL) | Default SURREAL | Mark if the dream felt real or fantastical. |
| `is_recurring` | Boolean | Default FALSE | Flag if the user believes this is a recurring theme. |
| `ai_insights_available`| Boolean | Default FALSE | Flag to indicate if Gemini analysis has been generated for this entry. |
| `created_at` | Timestamp | Not Null | System record creation time. |

**Metadata Sub-Fields (Stored in dedicated related tables or as structured JSON/separate columns for MVP simplicity):**

For MVP, complex metadata will be stored in separate, normalized tables or as structured JSON (`metadata_json`) within the `Dreams` table, depending on database flexibility, to facilitate easier querying later. Given the requirement for specific filtering, separate columns are preferred for core tags:

| Field Name | Data Type | Constraints / Notes | Purpose |
|---|---|---|---|
| `primary_emotion_tag` | String/Enum | Nullable | E.g., ANXIOUS, HAPPY, FEARFUL (for dashboard quick sort). |
| `primary_theme_tag` | String/Enum | Nullable | E.g., FLYING, CHASED, WATER (for dashboard quick sort). |
| `pre_sleep_stress_level` | Integer (1-5) | Nullable | Stress level before sleeping. |

---

### Table 3: DreamTags (Lookup/Junction for flexible tagging)

Allows users to select multiple emotions or themes per dream, addressing the questionnaire requirement for varied input.

| Field Name | Data Type | Constraints / Notes | Purpose |
|---|---|---|---|
| `dream_tag_id` | UUID/Serial | Primary Key | Unique ID for the tag instance. |
| `dream_id` | Foreign Key | Not Null, References Dreams(`dream_id`) | The dream being tagged. |
| `tag_type` | Enum (EMOTION, THEME) | Not Null | Defines if this is an emotion or a theme. |
| `tag_value` | String | Not Null | The specific tag value (e.g., \"Falling\", \"Joy\"). |

---

### Table 4: AIInsights

Stores the results generated by the Gemini API, segmented by insight type to match the required structured display on the detail page.

| Field Name | Data Type | Constraints / Notes | Purpose |
|---|---|---|---|
| `insight_id` | UUID/Serial | Primary Key | Unique identifier for the insight record. |
| `dream_id` | Foreign Key | Not Null, References Dreams(`dream_id`) | The dream this insight pertains to. |
| `insight_type` | Enum (SYMBOLIC, PSYCHOLOGICAL, RECURRING_MOTIF, EMOTIONAL_SUMMARY, TREND, CREATIVE_INSPIRATION) | Not Null | Categorization of the analysis generated. |
| `insight_content` | Text | Not Null | The processed text response from Gemini for this specific type. Optimized for concise display. |
| `generated_at` | Timestamp | Not Null | Time the insight was successfully generated. |
| `token_cost` | Integer | Optional | Useful for tracking usage against future paid tiers. |

4. RELATIONSHIP DIAGRAM SUMMARY

*   **User (1) <--> Dreams (M):** One user can have many dreams.
*   **Dream (1) <--> AIInsights (M):** One dream can trigger multiple structured insights (one per `insight_type`).
*   **Dream (1) <--> DreamTags (M):** One dream can have multiple theme/emotion tags applied via the junction table.

5. AI USAGE AND SUBSCRIPTION LOGIC

The MVP relies heavily on the `Users.ai_insights_used` counter.

1.  **Insight Generation Request:** When a user requests insights for a dream, the application first checks `Users.plan_status`.
2.  **Free Tier Logic:** If FREE, it checks if `ai_insights_used < 5`. If yes, generate the 6 required insight types, increment `ai_insights_used`, and set `Dreams.ai_insights_available = TRUE`. If no (>= 5), block generation and prompt upgrade.
3.  **Paid Tier Logic:** If PAID, generation proceeds regardless of the usage counter, as the counter will be reset based on the monthly billing cycle (`subscription_end_date`). The counter can still track usage for monitoring but does not gate access.
4.  **Data Security:** All `Users` data, especially passwords, must be handled via standard secure hashing (e.g., bcrypt). Sensitive user metadata within `Dreams` should be treated as PII requiring strong access controls inherent in the application logic (ensuring `user_id` authorization on every read/write).

6. MVP CONSTRAINT CONSIDERATIONS

*   **Token Limits:** The schema mandates storing insights separately (`AIInsights` table) to enforce concise, distinct responses per type, preventing Gemini from generating one massive, latency-heavy response block.
*   **Data Minimization:** The structure captures only necessary user interaction data (dream text, submission context, basic subscription status) minimizing raw data footprint for the free tier.
*   **Scalability (Future):** The use of UUIDs/Serial IDs is standard practice, ensuring that if the free DB tier needs upgrading, the primary keys remain stable. Normalization (via `DreamTags`) allows for complex theme/emotion analysis without requiring the `Dreams` table to explode in column count.

## User Flow
USERFLOW DOCUMENTATION: DreamSaver (MVP Focus)

1. OVERVIEW & GOALS
This document details the primary user flows for DreamSaver, focusing on the Minimum Viable Product (MVP) timeline (3-4 weeks, ₹0 budget). The core goals are seamless dream entry, secure storage, and initial AI interpretation delivery within the constraints of the free tier (5 insights limit).

2. USER PERSONAS
Target Audience: Self-aware individuals (16-35, students/young professionals) interested in self-growth and mental wellness, comfortable with technology and AI tools. They seek actionable insights from their dreams.

3. CORE USER FLOWS

---

3.1. Flow 1: First-Time User Experience (FTE) & Dream Submission (Guest Sign-Up)

Goal: Allow users to immediately capture a dream without friction, leading to automatic account creation.

| Step | User Action | System Response/View | Notes/Wireframe Description |
|---|---|---|---|
| 1.1 | User lands on the DreamSaver Landing Page. | Display aesthetic introduction, project features, and a prominent Dream Submission CTA/Text Box. | **Wireframe (Landing Page):** Dark, calming aesthetic (deep blues/purples). Central focus: Large, inviting text area labeled "Record Your First Dream..." Smooth entry animation. |
| 1.2 | User enters dream text (e.g., \"I was flying over a city made of glass.\"). | System prompts, or auto-detects intent to submit, potentially showing a subtle \"Sign Up/Save\" button. | Focus on immediate text capture. |
| 1.3 | User clicks "Submit" or equivalent. | **Modal/New Screen:** Dream Metadata Capture Form appears (still capturing the text from step 1.2). | **Wireframe (Metadata Form):** Clean, structured input fields. Fields must include Title (optional), Date/Time, Emotional Tone (tags/selection), Key Themes (tags/selection). Basic fields only for MVP. |
| 1.4 | User fills in mandatory metadata and clicks "Analyze & Save". | System initiates background user creation (email/passwordless login via secure token/local storage mapping if email is not required initially for MVP frictionlessness) and queues the dream for analysis. | **Security Note:** Ensure immediate, secure storage hashing. For MVP, user creation might rely on a secure session token linked to the first entry until explicit sign-up/login is enforced later. |
| 1.5 | Processing screen transition. | Brief, aesthetically pleasing transition screen (e.g., celestial animation) indicating AI processing. | Acknowledges Gemini latency constraints; manages user expectation. |
| 1.6 | Dream Saved Successfully. | User is redirected immediately to the **Dream Detail Page** for the newly entered dream, showing initial results. | This bypasses the Dashboard initially to immediately deliver value. The dashboard link is provided prominently. |

---

3.2. Flow 2: Reviewing Dreams on the Dashboard

Goal: Provide a clear overview of all recorded dreams and facilitate navigation.

| Step | User Action | System Response/View | Notes/Wireframe Description |
|---|---|---|---|
| 2.1 | User accesses the Dashboard (either redirected from Flow 1 or via navigation). | Display list of dream entries. | **Wireframe (Dashboard):** List or Card View. Each card shows: Date, Title Snippet, 1-3 Emotional Tags, and an AI Insight Status Indicator (e.g., a glowing icon if insights are available, a clock if pending). |
| 2.2 | User uses filtering/sorting tools. | The displayed list updates dynamically. | MVP Filters: Sort by Date (Newest/Oldest). Simple tag selection (e.g., show only 'Anxious' dreams). |
| 2.3 | User taps/clicks a specific dream entry. | System navigates to the Dream Detail Page for that entry. | Smooth transition, maintaining the dreamy aesthetic. |

---

3.3. Flow 3: Detailed Dream Review and AI Insight Consumption (Free Tier Constraint)

Goal: Present detailed dream data and structured, categorized AI insights, respecting the 5-insight limit.

| Step | User Action | System Response/View | Notes/Wireframe Description |
|---|---|---|---|
| 3.1 | User views the Dream Detail Page. | Displays Dream Content (Title, Text, Metadata). | **Wireframe (Detail Page Top):** Dream text area, metadata block (Date, Mood, Themes). |
| 3.2 | User views the AI Insight Section. | Displays categorized insights, respecting the remaining free insight count (e.g., "3/5 Insights Remaining"). | **Insight Structure Priority (MVP):** 1. Emotional Summary (Tags/Highlights). 2. Symbolic Analysis (Short interpretations per symbol). 3. Psychological Connection (Conversational paragraph). |
| 3.3 | User attempts to access a fourth insight type (e.g., Recurring Motif Identification). | System blocks access and displays an **Upgrade Prompt Overlay**. | **Upgrade Prompt:** Clear message stating: \"Free users receive 5 detailed insights. To unlock unlimited access and advanced analysis (like recurring motifs), upgrade now for ₹299/month.\" Contains CTA: "Upgrade Now". |
| 3.4 | User views past/future insights. | If the insight was generated previously (within the 5 limit), it displays. If it's a type not yet generated, it shows as available if the user upgrades. | Trend Insights and Creative Interpretations should be flagged as 'Premium' features upon first viewing the detail page if the limit is reached. |

---

3.4. Flow 4: Subscription Upgrade Path

Goal: Seamless transition from the free tier to the paid subscription.

| Step | User Action | System Response/View | Notes/Wireframe Description |
|---|---|---|---|
| 4.1 | User clicks "Upgrade Now" (from Flow 3 or via dedicated 'Plan' section). | Redirects to the Subscription Management Screen. | **Wireframe (Subscription Page):** Clear comparison: Free Plan (Unlimited Dreams, 5 Insights) vs. DreamSaver Pro (Unlimited Insights, Advanced Analysis) at ₹299/month. |
| 4.2 | User confirms selection and proceeds to payment. | Integration with Payment Gateway (e.g., Stripe/Razorpay stub for MVP). Collects payment details (Card/UPI). | MVP must handle the secure transaction. Ensure data minimization compliant with security requirements. |
| 4.3 | Payment successful. | System updates user status to 'Pro'. Confirmation message displayed. | User immediately gains access to unlimited insights. The insight counter resets/disappears. |
| 4.4 | User returns to Dashboard/Detail Page. | Insight generation requests (previously blocked) are now processed instantly for all dreams (if not already run). | System backend queues analysis for historical dreams using unlimited token access. |

---

4. NON-CORE (Administrative & Security) FLOWS

4.1. Data Management (Security Focus)

Goal: Ensure user control over their sensitive dream data.

| Step | User Action | System Response/View | Notes |
|---|---|---|---|
| 1. | User navigates to Account Settings/Privacy Center. | Displays current plan, option to manage subscription, and Data Controls. | Must be clearly accessible. |
| 2. | User selects "Edit Dream" on a specific entry. | Modal opens allowing modification of text and metadata. | Requires re-analysis prompt if text is significantly changed (consuming another insight credit if free user, or running instantly if Pro). |
| 3. | User selects "Delete Dream". | Confirmation modal ("Are you sure? This action cannot be undone."). | Must immediately purge all related data (dream text, metadata, and any generated insights) from the secure, encrypted database. |

4.2. Subscription Management (Cancellation/Renewal)

Goal: Allow users to easily manage billing details and cancel plans.

| Step | User Action | System Response/View | Notes |
|---|---|---|---|
| 1. | User accesses Subscription Management (via Settings). | Displays: Current Plan (Pro), Next Billing Date (e.g., Jan 15, 2024), Payment Method Last 4 Digits. | Includes a clear notification setting for renewal reminders (e.g., 3 days before). |
| 2. | User selects "Cancel Subscription". | Confirmation step explaining that access remains until the end of the current billing cycle. | Cancellation should be immediate in effect (no more renewal), but access persists until the paid period expires. |

## Styling Guidelines
# DreamSaver: Styling Guidelines Document

## 1. Design Philosophy: Celestial Calm

The styling for DreamSaver is rooted in creating a **dreamy, calming, and aesthetically pleasing** user experience. The primary goal is to provide an immersive environment that complements the reflective nature of dream journaling. We aim for a soft, minimal design that feels peaceful and slightly surreal, catering to our target audience of young adults interested in self-growth and wellness.

**Core Aesthetic Pillars:**
1. **Celestial & Nighttime Focus:** Deep, atmospheric colors evoking the night sky.
2. **Soft Minimalism:** Clean layouts with ample white (or dark) space, prioritizing content legibility.
3. **Subtle Immersion:** Gentle transitions, soft blurs, and non-jarring visual feedback.

## 2. Color Palette

The primary palette is designed around a **Dark Mode default** to enhance the nighttime, introspective mood.

| Color Name | Hex Code | Usage | Notes |
|---|---|---|---|
| **Primary Background (Deep Night)** | `#0A0A1A` | Main canvas color for Dark Mode. | Deep indigo/near-black. |
| **Secondary Background (Twilight)** | `#1F1B30` | Card backgrounds, modal surfaces, secondary panels. | Provides subtle contrast against the Deep Night. |
| **Primary Accent (Nebula Blue)** | `#8A2BE2` | Primary CTAs, active states, core iconography. | A deep, vibrant purple/blue for focus. |
| **Secondary Accent (Starlight Glow)** | `#B0C4DE` | Highlights, subtle borders, disabled states. | A soft, almost silvery blue for gentle accents. |
| **Text Primary (Clarity White)** | `#F0F0F0` | Main body text, primary headings. | High contrast for readability on dark backgrounds. |
| **Text Secondary (Faint Echo)** | `#A9A9A9` | Metadata, captions, secondary labels. | Used for supporting information. |
| **Emotional Highlight (Warmth)** | `#FFD700` | Used sparingly for positive tags/emotions (e.g., happy). | A soft gold/yellow for warmth. |
| **Emotional Highlight (Anxiety)** | `#DC143C` | Used sparingly for negative tags/emotions (e.g., anxious). | A muted, dark red. |

**Light Mode Consideration (Future/Fallback):** If a light mode is implemented, colors should invert: Primary Background becomes soft off-white (`#FAFAFA`), Primary Accent remains the deep purple (`#8A2BE2`), and Text Primary becomes the Deep Night (`#0A0A1A`).

## 3. Typography

Typography focuses on readability and a clean, modern feel that supports the minimal design. We prioritize sans-serif fonts that perform well across screen sizes.

**Font Family Selection:**
*   **Primary Font:** Inter or similar clean, highly readable sans-serif (e.g., Roboto, if Inter is unavailable on the MVP stack). This ensures excellent legibility for detailed dream entries and AI insights.

**Typographic Hierarchy:**

| Element | Font Size (Desktop) | Font Weight | Color | Line Height |
|---|---|---|---|---|
| **H1 (Page Title)** | 36px | Bold (700) | Text Primary | 1.2 |
| **H2 (Section Header - Insights)** | 24px | Semi-Bold (600) | Text Primary | 1.4 |
| **H3 (Dashboard Card Title)** | 18px | Medium (500) | Text Primary | 1.4 |
| **Body Text (General)** | 16px | Regular (400) | Text Primary | 1.6 |
| **Metadata/Caption** | 12px | Regular (400) | Text Secondary | 1.5 |
| **AI Insight Snippets** | 15px | Regular (400) | Text Primary | 1.55 |

## 4. Iconography and Visual Elements

Icons should be clean, line-based, and adopt the **Primary Accent** color when active or interactive.

*   **Style:** Minimalist, outlined icons (2px stroke weight recommended). Avoid heavy fills unless necessary for clarity (e.g., filled status indicators).
*   **Glow Effect:** Subtle, low-opacity radial gradients (using Nebula Blue) should be used around key interactive elements (like the main submission button or the AI Insight cards) to simulate a soft glow, enhancing the dreamy atmosphere.

## 5. UI/UX Principles

The interaction design must reinforce the calm and immersive nature of the application.

### 5.1. Navigation and Layout

*   **Minimalism:** Layouts should be sparse, utilizing generous padding and margins. Content should breathe.
*   **Dashboard Display:** Dream cards must adhere strictly to the summarized format: Date, Snippet (truncated to 2 lines), Emotional Tags (small, colored pills), and AI Insight Status Indicator.
*   **Smooth Transitions:** All page navigations, modal openings, and state changes (e.g., loading AI insights) must use gentle transitions (e.g., subtle fades or slow sliding) rather than instant cuts, simulating the fluidity of dreams.
*   **Blur Effects:** Use soft background blurs (`backdrop-filter: blur(10px);`) on modals and fixed headers when overlying dynamic content to enhance the atmospheric, layered feeling.

### 5.2. Dream Submission Experience (Landing Page & Entry)

*   The main text input area should feel expansive. Placeholder text should be inviting (e.g., "Describe where you floated last night...").
*   **Metadata Input:** Metadata fields (emotional tone, themes) should utilize friendly UI elements like tags or toggle switches rather than complex dropdowns. These tags use the secondary accent colors or emotional highlights.
*   **Loading State:** When awaiting AI analysis (post-submission), display a calming loading animation (e.g., softly pulsing stars or a slow gradient shift) instead of a standard spinner, reinforcing the "waiting for insight" mood.

### 5.3. AI Insight Presentation (Detailed Dream Page)

This is critical for usability, as AI data must be digestible. Insights must be separated into distinct, digestible modules based on type:

1.  **Symbolic Analysis:** Presented as a bulleted list or small definition cards (Symbol: Interpretation). Uses clear headers (H3).
2.  **Emotional Summary:** Displayed prominently as colored tags or a sentiment meter visualization near the top metadata.
3.  **Psychological Connections:** Presented in slightly longer, dedicated paragraph blocks with clear conversational headers ("Connecting to Your Day").
4.  **Recurring Motif/Trend Insights:** Displayed using actionable links or small charts/visual summaries. If links to past dreams are provided, they should use the Secondary Accent color for differentiation.

**Constraint Management Display:** The UI must clearly display remaining free AI insights (e.g., "5/5 Insights Remaining") near the top of the dashboard or detail view, using the Primary Accent color to draw attention without being intrusive.

### 5.4. Subscription & Management UI

The upgrade flow must be extremely clear and reassuring, given the sensitive nature of the data and the focus on wellness.

*   **Clarity:** Use clear labeling for the Free Tier vs. Paid Tier benefits (Unlimited Insights).
*   **Pricing Display:** The ₹299/month price point should be clearly displayed using the Primary Accent color.
*   **Management:** Subscription settings must feature large, unambiguous buttons for "Cancel Subscription" (perhaps using a muted red) and "Manage Payment Details."

### 5.5. Accessibility Note (MVP Consideration)

While focused on aesthetics, the MVP must ensure essential WCAG contrast standards are met, especially for the Primary Background (`#0A0A1A`) and Text Primary (`#F0F0F0`). Text secondary and colored tags should be checked against AA standards where possible, prioritizing readability over purely atmospheric color choices for critical information.
