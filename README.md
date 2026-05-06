A fully functional, frontend-only complaint management platform built with vanilla HTML, CSS, and JavaScript — no frameworks, no backend, no dependencies beyond Chart.js.
</div>

Overview
SCMS is a role-based complaint tracking system designed for institutions (universities, offices, housing societies). Users can file complaints with priority levels and track their status in real time. Admins get a full analytics dashboard with live charts, filtering, and CSV export.
Everything runs in the browser using LocalStorage as the persistence layer — no server required.

Pages
FileRoleDescriptionindex.htmlPublicLogin / Register page with role selection and demo accountsuser-dashboard.htmlUserView and track personal complaints with status timelinesubmit-complaint.htmlUserMulti-field complaint form with live preview, priority picker, drag-and-drop file zoneadmin-dashboard.htmlAdminAnalytics dashboard with charts, full complaint table, status management, CSV export

Features
Authentication

Login and Register with client-side validation
Role-based routing — users and admins land on different dashboards
Session persistence via LocalStorage
One-click demo login (no registration needed to try the app)
Active nav suppression — current page link is non-clickable

User Side

Submit complaints with title, category, location, description, priority, and file attachments
Live complaint preview card updates as you type
Character count on description field
Track all personal complaints with status badges (Pending / In Progress / Resolved)
Animated status timeline per complaint

Admin Side

Real-time stats: total complaints, pending, in progress, resolved, resolution rate %
Three Chart.js charts: status doughnut, category bar, priority doughnut
Full complaints table with search, status filter, and priority filter
Inline status update via dropdown — updates charts and stats immediately
CSV export of all complaints with one click
Toast notifications for all actions

UI & UX

Dark theme throughout with CSS custom properties (--accent: #e8ff47, --accent2: #7c6aff)
Google Fonts: Syne (headings) + DM Sans (body)
Smooth animations: fadeUp on stat cards, float on preview cards, slideUp on auth box
Animated pulsing status indicator on login page
Responsive — login page collapses left panel on mobile (max-width: 900px)


Tech Stack
TechnologyUsageHTML5Page structure and semantic markupCSS3Custom properties, grid, flexbox, keyframe animationsVanilla JavaScriptDOM manipulation, LocalStorage CRUD, form validation, CSV generationChart.js v4.4.1Doughnut and bar charts on admin dashboardGoogle FontsSyne + DM Sans typefaces
No build tools. No npm. No frameworks. Open index.html directly in a browser.

Getting Started
Option 1 — Open directly
bash# Clone the repo
git clone https://github.com/UniversalPrince/SCMS.git
cd SCMS

# Open in browser (double-click or use any local server)
open index.html
Option 2 — Live Server (VS Code)

Install the Live Server extension in VS Code
Right-click index.html → Open with Live Server

Demo Credentials
RoleEmailPasswordUseruser@demo.comdemo123Adminadmin@demo.comdemo123
Or use the Demo User / Demo Admin buttons on the login page — no typing needed.

SCMS/
├── index.html              # Login & Register
├── user-dashboard.html     # User complaint tracker
├── submit-complaint.html   # Complaint submission form
├── admin-dashboard.html    # Admin analytics & management
└── README.md
How Data Works
All data is stored in the browser's LocalStorage under these keys:
KeyContentsscms_usersArray of registered user objectsscms_sessionCurrently logged-in user objectscms_complaintsArray of all submitted complaints
Each complaint object contains: id, title, category, location, description, priority, status, submittedAt, updatedAt, userId, userName.
To reset all data, open DevTools → Application → LocalStorage → Clear all.

What I Learned

Managing multi-page state without a backend using LocalStorage
Role-based routing and session management in vanilla JS
Integrating Chart.js with dynamic, real-time data
Building a full CRUD interface (create complaints, read/filter, update status, delete via clear) without any library
Generating and downloading CSV files programmatically in the browser
CSS custom properties for consistent dark theming across multiple pages
Handling drag-and-drop file input with visual feedback


Author
Prince Raj
B.Tech CSE (Data Science) — Galgotias University
