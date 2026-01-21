# UCSW001: Design Database Structure

This use case describes the **design process for database structures**.

It is based on the following assumptions:
- A custom software component is developed in the telecom domain.
- The component requires a database to store business resources.

---

## Identification of domain / sub-domain / process

Based on business requirements, the developer should identify the relevant **TM Forum domain and process**.

This step helps to:
- Map the new component to the TMF Functional Framework
- Align it with ODA component mappings in the future

### Prerequisites
- MCP server with knowledge of eTOM and the Functional Framework  
- AI agent with access to MCP  
- Prepared prompts for domain/process identification  

### How to
The developer sends all business requirements to the AI agent to identify the appropriate eTOM domain and process.

### Validation
- The AI agent should return a full description of the selected domain/process, including links to relevant documentation.
- The developer is responsible for verifying that the AI agent made the correct decision.

---

## Identification of resources and attributes

Based on business requirements and the identified eTOM domain/process, the developer should identify relevant **resources and their attributes**.

### Prerequisites
- MCP server with knowledge of the Information Framework  
- AI agent with access to MCP  
- Prepared prompts for analysis  

### How to
- The AI agent presents a list of resources and attributes relevant to the business requirements within the specified eTOM process.
- The developer selects a subset of these resources and prepares an initial draft of the database structure.

> Note: The Information Framework provides a logical data model. The physical database schema may differ.

- The developer should adapt the proposed data schema based on:
  - Non-functional requirements (NFRs)
  - Database engine constraints and specifics

### Validation
- The AI agent should be able to compare the physical data schema (for example, SQL DDL) with the resources and relationships defined in the Information Framework.
- Based on the AI agent’s feedback, the developer decides whether:
  - The data schema fully covers current business requirements
  - The schema is ready for future extension