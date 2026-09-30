Svijet malih ljudi — Kindergarten Child Development Tracker

Desktop application for kindergartens to replace paper-based record-keeping with a digital system for tracking children's development, group management, 
and activity planning. Built as a final thesis project (C++Builder / RAD Studio).

Tech Stack
- C++Builder (VCL) — desktop UI, event-driven architecture
- MySQL + FireDAC — relational data access layer
- JSON / XML / custom binary format — used for data kept outside the database (health records, announcements, child profile export/import)
- REST (HTTP) — live weather forecast integration (Open-Meteo)
- Multithreading (thread pool) — parallel batch generation of development recommendations
- SHA-256 — salted password hashing

Key Features
- Role-based access control (admin, director, educator, specialist) with per-role permission checks
- Full CRUD for children, groups, and activities, with filtering/sorting
- Periodic child development assessments and automatic, rule-based recommendation generation (individually or in parallel batches for an entire group)
- Health record tracking with automatic epidemic/absence warnings
- Announcements board with priority color-coding and countdown
- Group reports with hand-drawn charts and PDF export
- Binary file export/import for transferring a child's development profile between kindergartens using the system

Notable Engineering Details
- Parameterized SQL queries throughout to prevent SQL injection
- Thread pool used for batch recommendation generation — parallel processing reduced execution time significantly for larger groups
- Graceful degradation when offline (weather API failure doesn't affect other functionality)
- Passwords stored as SHA-256 hash + per-user salt, never in plain text
