 ```mermaid 
 flowchart TD
    %% Authentication
    User["👤 User"] --> Auth["🔐 Authentication via Azure AD / SSO"]
    Auth --> Dashboard["🖥️ AI Agent Management Dashboard"]

    %% Section 1: Task Execution
    Dashboard --> TaskExec["▶ Task Execution\n(Run AI Tasks)"]
    TaskExec --> AIEngine["🧠 AI Processing\n(Vertex AI / Azure Foundry)"]
    AIEngine --> DataSources["📂 Data Sources\n(SQL, SharePoint, APIs, Cloud Storage)"]
    DataSources --> AIEngine
    AIEngine --> Results["📊 Results Returned to User"]
    Results --> History["📜 View Task History"]

    %% Section 2: Agent Creation
    Dashboard --> AgentCreation["➕ Create New AI Agent"]
    AgentCreation --> Configure["⚙️ Configure Agent Settings\n(Basic + Advanced)"]
    Configure --> ReadyAgent["🧩 Agent Ready to Use"]
    ReadyAgent --> TaskExec

    %% Section 3: Recent Activity
    Dashboard --> Recent["📂 Recent Agent Activity Log"]
    TaskExec --> Recent
    AgentCreation --> Recent

    %% Observability
    Results --> Observability["📈 Observability & Audit\n(Logs, Metrics, Traces)"]
    Recent --> Observability
