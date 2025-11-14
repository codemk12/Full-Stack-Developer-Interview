# Full Stack Developer Take-Home Task: Vehicle Lead Manager

Thank you for taking the time to complete our take-home task. This exercise is designed to give you a chance to demonstrate your skills in a practical, real-world scenario.

## Objective

Build a simple, full-stack web application to display, create, update, and delete sales leads for a vehicle dealership.

The core of this task is to build a RESTful API, connect it to a database, seed that database with the provided data, and build a UI to interact with it.

## Scenario

Our dealership needs an internal tool to manage potential customer leads. We have an initial list of leads (50 entries) hosted externally, and we need an application that allows our sales team to:

- See all the current leads on a dashboard.
- Change the status of a lead (e.g., from 'New' to 'Contacted').
- Add a brand new lead that just called in.
- Remove a lead that is no longer valid.

## Core Requirements

### 1. Initial Dataset (50 Leads)

The initial dataset of approximately 50 leads is hosted externally. Your application must be able to retrieve this data and populate your database when it first runs (data seeding).

**DATASET LINK:**

https://gist.githubusercontent.com/codemk12/3691a622ba446e4e39d0e80ece702a44/raw/leads.json

The data will follow this structure (a single array of lead objects):

```json
[
  {
    "id": "f4f2a8d1-7253-461b-9d4f-b6a4a1a3b8e8",
    "firstName": "John",
    "lastName": "Doe",
    "email": "john.doe@example.com",
    "phone": "555-1234",
    "vehicleOfInterest": "2024 Toyota Camry",
    "status": "New"
  }
  // ... approximately 49 more lead objects
]
```

### 2. Backend (API)

- **Technology:** Use any backend framework you are comfortable with (e.g., Node.js/Express, Python/Django/FastAPI, Go, Java/Spring Boot, etc.).

- **Database:** Use any database of your choice (e.g., PostgreSQL, MySQL, MongoDB, or SQLite).

- **Data Seeding:** Write a script or mechanism that downloads the JSON data from the provided Gist link and populates the database with the 50 leads on application start-up (but only if the database is empty). This tests external data fetching.

- **Data Model:** Your Lead model must include:
  - `id` (String/UUID)
  - `firstName` (String)
  - `lastName` (String)
  - `email` (String)
  - `phone` (String)
  - `vehicleOfInterest` (String)
  - `status` (String - e.g., 'New', 'Contacted', 'Qualified', 'Lost')

- **API Endpoints:** Create the following RESTful endpoints:
  - `GET /api/leads` - Retrieve all leads (this will power the dashboard).
  - `POST /api/leads` - Create a new lead.
  - `PUT /api/leads/:id` - Update an existing lead. The main use will be to change the status.
  - `DELETE /api/leads/:id` - Delete a lead.

### 3. Frontend (UI)

- **Technology:** Use a modern frontend framework (e.g., React, Vue, Angular, Svelte).

- **Views:** The application should have two main functionalities:

  **Lead Dashboard (Main View):**
  - Display all 50+ leads from the `GET /api/leads` endpoint (from your database).
  - Show all the lead's information in a table or list of cards.
  - For each lead, add a dropdown menu (or similar UI) to change its status. This must trigger a PUT request to your API.
  - For each lead, add a delete button. This must trigger a DELETE request to your API.

  **Lead Capture Form (New View/Modal):**
  - Create a simple form to add a new lead.
  - Submitting this form must trigger a POST request to your API. The new lead should then appear on the dashboard.

## Bonus Points (Optional)

If you have extra time, here are some ways to impress:

- **Input Validation:** Add validation on both the frontend (e.g., "Email is required") and backend.
- **Styling:** Make it look clean and professional using a UI library (e.g., Material-UI, Tailwind CSS, Bootstrap) or your own CSS.
- **Filtering & Search:** Implement client-side or server-side filtering (by Status) and searching (by Name/Email) on the dashboard to handle the 50+ entries efficiently.
- **Testing:** Write a few simple unit tests for your API or frontend components.
- **Containerization:** Include a Dockerfile and docker-compose.yml to make the application easy to run.

## Evaluation Criteria

We will be looking at:

- **Functionality:** Does the app work? Do all C.R.U.D. (Create, Read, Update, Delete) operations function correctly?
- **Data Handling:** Does the app correctly download and seed the database from the external Gist link?
- **Code Quality:** Is the code clean, well-organized, and easy to understand?
- **Full Stack Integration:** Do the frontend and backend communicate properly?
- **Documentation:** A clear README.md explaining how to set up and run your project.

## Submission

Please place your code in a private GitHub repository and invite the hiring manager (codemk12) as a collaborator.

Good luck!
