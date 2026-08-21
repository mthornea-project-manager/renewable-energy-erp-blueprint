# 📋 Module: Sales Pipeline & Opportunity Management (Kanban)

## 1. Module Objective
To digitalize and automate the sales workflow for photovoltaic and aerothermal installations, minimizing technical response times and improving conversion rates through end-to-end traceability of each commercial stage.

## 2. Workflow Definition (Kanban States)
The system manages opportunities through a Kanban board featuring the following critical stages:
1. **Request:** Initial lead registration and capture of basic client data.
2. **Pending Site Survey:** Scheduling of technical field visits and on-site data collection.
3. **Technical Validation:** Review by the Technical Director (load calculations, inverter/heat pump sizing).
4. **Estimation & Proposal:** Generation of commercial documentation including ROI estimation and energy savings projections.
5. **Closing:** Conversion to an active installation project.

## 3. Data Structure (Conceptual Schema)
To build the underlying database, each `Opportunity` entity will contain:
* `id`: Unique identifier (UUID).
* `client_name`: Client full name or corporate entity.
* `status`: (Enum: [Request, Site_Survey, Technical_Validation, Proposal, Closing]).
* `energy_type`: (Enum: [Photovoltaic, Aerothermal]).
* `capacity_kw`: Estimated system capacity in kilowatts (float).
* `assigned_tech`: ID of the assigned technical specialist.
* `updated_at`: Timestamp of the last status modification.

## 4. Suggested Technology Stack (Architecture)
* **Frontend:** React.js utilizing `react-beautiful-dnd` for fluid drag-and-drop Kanban card management.
* **Backend:** Python (FastAPI) to handle business logic, state validations, and routing.
* **Database:** PostgreSQL to ensure robust transactional integrity for financial and technical data.
* **Security:** Role-Based Access Control (RBAC) to differentiate permissions between sales representatives and the Technical Director.
