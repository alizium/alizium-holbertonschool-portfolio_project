0. Plans and sprints

The purpose of this phase was to divide the Expiry Tracker MVP development into short, manageable iterations in order to ensure continuous progress, iterative testing, and flexibility.
By applying Agile principles, the work was organized in a way that each sprint produced concrete, testable deliverables that progressively built the final product.



The Expiry Tracker project aims to help users track the expiration dates of their personal or professional items and receive reminders before those dates.
The MVP includes:

Secure user authentication (register, login, password management).

CRUD operations for items with expiration dates.

Email notifications and password reset via nodemailer.

A minimal frontend interface connected to the backend API.

To develop this product efficiently, the work was split into two sprints, following the Agile Scrum methodology.

Sprint Planning Methodology

The project was planned using the MoSCoW prioritization framework, which classifies tasks as:

Must Have: Essential features required for the MVP to function.

Should Have: Secondary features that improve usability or maintainability.

Could Have: Optional features that add value but are not critical.

Won’t Have: Features deliberately postponed for future versions.

Each sprint had a duration of one week, ensuring focused, achievable goals and quick feedback cycles.

Sprint Structure :

| Sprint    | Duration  | Main Objective                                    | Deliverables                                                        |
|-----------|-----------|---------------------------------------------------|---------------------------------------------------------------------|
| Sprint 1  | 1 week    | Backend foundation, authentication, and security  | Functional API (Auth + Items CRUD), database setup, Postman tests    |
| Sprint 2  | 1 week    | Frontend integration, email features, and testing | Connected frontend, email reminders, QA validation, and final documentation |



1. Development Tasks
Purpose

The purpose of this stage was to implement the MVP features defined in the sprint plan.
Following the Agile methodology, each sprint was dedicated to specific development goals — transforming the technical documentation and diagrams from Stage 3 into working, testable features.

This phase focused on building, testing, and refining the code according to predefined priorities and coding standards.

Overview of the Development Phase

The development was divided into two sprints, each lasting one week, covering both backend and frontend implementation.

Sprint 1: Focused on building a secure backend with authentication, CRUD operations, and API documentation.

Sprint 2: Focused on frontend integration, email automation, and quality assurance testing.


The workflow followed the Agile cycle:

Development of features in feature branches.

Review and merge into the dev branch by the SCM role.

Testing and validation by QA before merging into main.

Agile Sprint Execution
Sprint 1 — Backend Development & Security

Objectives:

Build the core API.

Implement database models.

Ensure authentication, validation, and documentation.

Tasks executed:

#	Task	Description	Status
1	Initialize backend structure	Created project with Express + Sequelize
2	Configure database connection	PostgreSQL via Sequelize (config/db.js)
3	Create models	User, Item, PasswordReset models
4	Implement authentication routes	/api/auth/register, /api/auth/login, /api/auth/forgot-password, /api/auth/reset-password
5	Add JWT middleware	Authentication with requireAuth middleware
6	Implement CRUD for items	/api/items (GET, POST, PUT, DELETE) restricted by user ID
7	Configure security middlewares	Helmet, CORS, and Rate-Limiting
8	Setup Swagger documentation	Added /api/docs for API documentation
9	Write Postman tests	Verified endpoints and error handling

2. Monitor Progress and Adjusting
Purpose

The purpose of this stage was to monitor the project’s progress, identify potential blockers early, and ensure the sprints stayed aligned with the initial objectives defined during planning.
Monitoring allowed continuous adaptation of the schedule and priorities, following the Agile principle of flexibility and iterative improvement.

This step ensured that each sprint led to tangible progress while maintaining quality and respecting the MVP scope.

Monitoring Approach

Progress was tracked daily through Agile metrics and simple tools for task visualization and issue management.
Since the project was individual, daily self-assessment replaced team stand-ups, but the same principles were applied:

Review of completed tasks.

Identification of blockers.

Adjustment of priorities.

Re-estimation of remaining workload.

Tools used:

Trello Board for task tracking (Backlog → In Progress → Done).

GitHub for issue tracking and version control monitoring.

Postman and console logs for debugging and progress validation.


What obstacles exist:
Identification of issues such as CORS errors, authentication bugs, or database conflicts.

This method kept focus, prevented overload, and ensured every commit moved the project forward.

| Metric                   | Description                               | Sprint 1  | Sprint 2 |
|--------------------------|-------------------------------------------|-----------|-----------|
| **Velocity**             | Number of tasks completed per sprint      | 12        | 12        |
| **Planned vs Completed** | Ratio of completed vs planned tasks       | 85 %      | 100 %     |
| **Bugs Opened / Closed** | Logged issues resolved per sprint         | 6 / 5     | 3 / 3     |
| **CI Build Pass Rate**   | GitHub Actions workflow result            | 100 %     | 100 %     |
| **Postman Tests Passed** | Manual endpoint validations               | 100 %     | 100 %     |




3. Conduct Sprint Reviews and Retrospectives
Purpose

The purpose of this phase was to review the progress of each sprint, present the work completed, and conduct a retrospective to identify successes, challenges, and areas for improvement.
This step ensured that each sprint ended with a clear understanding of what was achieved and how future iterations could be improved, following the Agile continuous improvement principle.


Methodology :

At the end of each sprint, a Sprint Review and a Sprint Retrospective were conducted.

The Sprint Review focused on demonstrating the functional features completed during the sprint.

The Sprint Retrospective focused on team performance analysis, identifying what went well, what didn’t, and how to improve in the next sprint.

Even though the project was developed individually, these steps were maintained to ensure a structured evaluation process and personal accountability, similar to a real Agile environment.

Sprint Review – Overview
Sprint 1 – Backend Foundation & API Delivery


sprint review features :

Authentication (register, login, password management).

JWT-based authorization middleware protecting the /api/items routes.

CRUD operations on items (create, read, update, delete).

Database synchronization through Sequelize.

Security layers (Helmet, CORS, Rate Limit).

API documentation with Swagger UI at /api/docs.

Testing Evidence:

All endpoints tested with Postman and validated manually.

Integration tests (Jest + Supertest) passed successfully.

Errors such as “unauthorized access” were handled properly.

Feedback and Adjustments:

CORS needed refinement for frontend compatibility.

Added stricter validation rules with express-validator.

Improved token error handling for invalid or expired tokens.

Sprint 2 – Frontend Integration & Reminders

Objective:
Connecting the frontend to the backend API, implement email notifications, and finalize QA validation.

Demo Summary:

Login and Registration pages integrated with backend endpoints.

Dashboard displaying user-specific items fetched from /api/items.

Item creation, update, and deletion actions working seamlessly.

Password reset feature via email (using Nodemailer).

Automatic reminder emails (J-7, J-3, J-1) executed with node-cron.

Fully functional MVP with frontend and backend communication.

Testing Evidence:

Frontend tested locally via live server.

Postman validated all API flows with live backend.

Email reminders verified through console logs.

Feedback and Adjustments:

Improved user feedback with alert messages and loaders.

Added error redirection for expired tokens.

Refined .env.example and deployment instructions.

Retrospective – Reflection and Improvements

After each sprint, a retrospective review was held to analyze the overall workflow and outcomes.
This helped improve both technical and organizational aspects of the project.

Sprint 1 Retrospective
Aspect	Observation
What worked well	Clear sprint goals and manageable workload. The backend architecture was clean and modular. Documentation (Swagger + README) helped maintain clarity.
What didn’t work well :	Some environment variables (SMTP, JWT_SECRET) caused delays due to configuration issues.
What to improve	: Creating a .env.example early in Sprint 1. Implementing a basic CI test to automate backend validation. = completed

4. Final Integration and QA Testing
Purpose

The purpose of this final phase was to verify that all components of the MVP work together seamlessly, ensuring functional, stable, and secure integration between the backend, frontend, and database.
This stage focused on Quality Assurance (QA), integration testing, and final validation of the Expiry Tracker MVP before delivery.

The ultimate goal was to confirm that the system met both the technical requirements and user expectations defined during the previous stages.

Integration Overview

After completing both sprints, all modules of the Expiry Tracker were successfully integrated into a unified system:

Component	Description	Integration Result
Backend (Node.js + Express)	Provided API endpoints for authentication, CRUD items, and email operations	Fully functional and secured
Database (PostgreSQL)	Managed all persistent data via Sequelize models	Connected, synced, and validated
Frontend (HTML + JS + CSS)	Provided user interface for interaction with backend	Successfully connected to API
Email Service (Nodemailer)	Sent password reset and expiration reminders	Working in console (dev mode)
Scheduler (node-cron)	Triggered daily checks for expiring items	Operational and logged daily
CI/CD (GitHub Actions)	Automated testing workflow for backend	Passed all builds successfully


5. Deliverables
Purpose

This final section summarizes all tangible outputs and documentation produced during Stage 4.
It confirms that all sprints, code implementations, QA tests, and integration tasks were successfully completed and validated according to the project requirements.
