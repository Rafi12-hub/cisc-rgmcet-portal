# cisc-rgmcet-portal
CISC is a premium, student-driven academic ecosystem developed for the **Computer & Information Science Club (CISC)** at **Rajeev Gandhi Memorial College of Engineering and Technology (RGMCET)**. The platform is designed to bridge the gap between classroom curriculum and industry expectations through senior-to-junior mentorship, hands-on workshop scheduling, and performance tracking.

## 🚀 Key Features & Business Rules
### 1. The 7 CISC Sub-Clubs
Students can select their specialized engineering track from the 7 custom-defined sub-clubs:
*   **Placement Guidance Club:** Focuses on resume-building workshops, ATS formatting, and technical/HR mock interviews.
*   **Communication, GD & Debate Club:** Targets public speaking skills, stage fear reduction, group discussions, and debates.
*   **Digital Professional Skills Club:** Tool-focused training covering Git, GitHub, LinkedIn branding, and AI productivity.
*   **Hackathon & Innovation Club:** Conducts internal bootcamps and rapid prototyping to prepare students for national events like the Smart India Hackathon (SIH).
*   **Technical Skill Development Club:** Implements a syllabus beyond the academic curriculum (e.g., MERN stack, Docker, APIs).
*   **ZEN Club:** Academic stress-relief recreation through meme contests, gaming tournaments, and standup open mics.
*   **H2H Club (Heart to Heart):** Fosters humanitarian values through donation collections, orphanage visits, and rural community outreach.
### 2. Core Business Rules
*   **Single-Club Constraint:** A student is restricted to joining or requesting only **one active club** at any given time. If they try to register for another club, the system intercepts it and displays a warning to leave their current active/pending club first.
*   **1-Month Expiry Rule:** Membership in a club lasts for exactly **one month** from the date of approval. The system automatically calculates the expiration date (`expires_at`) when approved and marks the membership as `expired` in real time once the duration completes, opening up the student's slot to join a new domain.
### 3. Role-Based Dashboards
*   **Public Guest (Unauthenticated):** Access to view active sub-clubs, scheduled workshops/events, and the student Wall of Achievements.
*   **Student Console:** Allows students to update profile bios, register/unregister for upcoming events, view active membership expiration dates, and monitor earned merit leaderboard points.
*   **Faculty Incharge Console:** Assigned to club faculty heads. Allows overseeing their specific club roster, reviewing pending registration approvals, tracking membership expiration dates, and reviewing student achievement milestones.
*   **System Administrator Console:** Central admin panel for creating or editing sub-clubs, assigning faculty heads, tracking the member directory, scheduling events, and awarding leaderboard points to outstanding students.
---
## 🛠️ Technology Stack
*   **Frontend Library:** React (Single Page Application architecture)
*   **Build Tool:** Vite (Ultra-fast Hot Module Replacement)
*   **Styling:** Vanilla CSS with custom layout tokens (Flexbox/CSS Grid), glassmorphism styles, and animated aurora backgrounds.
*   **Icons:** Lucide React
*   **Database:** Integrated Firebase SDK with LocalStorage fallback for instant standalone offline operations.
---
## 📦 Getting Started
### Prerequisites
Make sure you have [Node.js](https://nodejs.org/) installed on your machine.
### Installation
1. Clone this repository locally.
2. Open your terminal in the project directory.
3. Install the dependencies:
   ```bash
   npm install
   ```
### Database Integration (Firebase Setup)
1. To connect to Firebase, create a `.env.local` file in the root directory.
2. Add your Firebase web app configuration keys:
   ```env
   VITE_FIREBASE_API_KEY=your_api_key
   VITE_FIREBASE_AUTH_DOMAIN=your_auth_domain
   VITE_FIREBASE_PROJECT_ID=your_project_id
   VITE_FIREBASE_STORAGE_BUCKET=your_storage_bucket
   VITE_FIREBASE_MESSAGING_SENDER_ID=your_messaging_sender_id
   VITE_FIREBASE_APP_ID=your_app_id
   VITE_FIREBASE_MEASUREMENT_ID=your_measurement_id
   ```
### Running Locally
To launch the hot-reloading local development server:
```bash
npm run dev
```
Open **[http://localhost:5173](http://localhost:5173)** in your browser to view the application.
### Building for Production
To bundle and optimize the project assets for deployment:
```bash
npm run build
```
The compiled, production-ready static outputs will be generated in the `/dist` directory.
---
## 🧪 Developer Role Switcher
For quick testing and grading of the various dashboard perspectives, we have integrated a floating **Portal Roles Tester** switcher in the bottom-right corner of the application:
*   **Public:** Unauthenticated guest view.
*   **Student:** Automatically logs in as `Rahul Sharma` (CSE - 3rd Year) with a clean slate of `0` starting points.
*   **Incharge:** Automatically logs in as `Mrs. M. Sravani` (Faculty Incharge of the Communication, GD & Debate Club).
*   **Admin:** Automatically logs in as `Prof. K. Prasad` (General Administrator / CSE Head).
---
## 📁 File Structure
```text
├── index.html          # Main HTML entry point
├── package.json        # Project metadata and dependencies
├── vite.config.js      # Vite project bundler settings
├── public/             # Static public assets
└── src/
    ├── main.jsx        # App mounting script
    ├── App.jsx         # Root router and role-handling switcher
    ├── style.css       # Core design system tokens, layout classes, and animations
    ├── components/
    │   ├── Common.jsx  # Reusable GlassCards, Navbars, Sidebars, and Aurora Backgrounds
    │   └── firebase.js # Firebase app initialization logic
    ├── services/
    │   └── dbService.js# Database queries, updates, and auto-expiration cron scripts
    └── pages/
        ├── Public.jsx  # Public pages (Home, Clubs list, Events calendar, Achievements, Login page)
        ├── StudentDashboard.jsx # Student console tabs (Overview, Clubs, Events, Announcements, Profile)
        ├── InchargeDashboard.jsx# Faculty panel (Pending approvals, rosters with expiry date, events timeline)
        └── AdminDashboard.jsx   # Admin panel (Control board for clubs, member lists, events, point awards)
```
