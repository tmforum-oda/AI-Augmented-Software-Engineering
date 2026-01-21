# UCSW002: Implement TM Forum Open API

This use case describes how an **AI agent skill assists developers in implementing a TM Forum Open API** in their target programming language.

It is based on the following assumptions:
- The developer wants to implement a specific TM Forum Open API (e.g., TMF620, TMF629)
- The implementation should conform to the official OpenAPI specification
- The target language is Python, Node.js, or Rust

---

## Identification of Target API

The developer provides the TM Forum API number (e.g., TMF620 for Product Catalog Management API).

### Prerequisites
- AI agent skill with access to TM Forum Open API specifications
- Access to the [TM Forum Open API GitHub repository](https://github.com/tmforum-apis/Open_Api_And_Data_Model)

### How to
1. The developer specifies the API number (e.g., `TMF620`)
2. The AI agent retrieves:
   - OpenAPI specification (YAML/JSON)
   - JSON Schema definitions for data models
   - API documentation and conformance requirements

### Validation
- The agent confirms the API exists and displays:
  - API name and version
  - Brief description
  - List of available endpoints

---

## Technology Stack Selection

The developer selects the target programming language and the agent uses the appropriate framework.

### Supported Stacks

| Language | Framework | Use Case |
|----------|-----------|----------|
| Python | FastAPI | Async REST APIs with automatic OpenAPI docs |
| Node.js | Express | Lightweight, widely-adopted web framework |
| Rust | Axum | High-performance, type-safe web services |

### How to
- The developer specifies the target language
- The agent selects the corresponding framework and generates idiomatic code

---

## Code Generation

The AI agent generates server implementation stubs based on the OpenAPI specification.

### Prerequisites
- Selected API specification (from step 1)
- Target technology stack (from step 2)

### Generated Artifacts

1. **Data Models**: Classes/structs representing API resources (e.g., `ProductOffering`, `Catalog`)
2. **Route Handlers**: Endpoint stubs for each API operation (GET, POST, PATCH, DELETE)
3. **Request/Response Validation**: Schema validation using the TM Forum data models
4. **Project Structure**: Recommended folder layout for the implementation

### Example: TMF620 Product Catalog Management API

For TMF620 with Python/FastAPI, the agent generates:

```
tmf620-product-catalog/
├── app/
│   ├── main.py              # FastAPI application entry point
│   ├── models/
│   │   ├── catalog.py       # Catalog data model
│   │   ├── category.py      # Category data model
│   │   └── product_offering.py
│   ├── routes/
│   │   ├── catalog.py       # /catalog endpoints
│   │   ├── category.py      # /category endpoints
│   │   └── product_offering.py
│   └── schemas/             # Pydantic schemas from JSON Schema
├── tests/
├── requirements.txt
└── README.md
```

### How to
1. The agent parses the OpenAPI specification
2. Generates data models from JSON Schema definitions
3. Creates route handlers for each endpoint
4. Implements request/response validation
5. Provides a runnable project skeleton

---

## Validation

The implementation should be validated against the TM Forum specification.

### Validation Steps

1. **Schema Compliance**: Verify generated models match TM Forum JSON Schema
2. **Endpoint Coverage**: Ensure all required endpoints are implemented
3. **Response Format**: Validate response structures against specification
4. **Conformance Preparation**: Identify gaps for TM Forum Open API conformance certification

### How to
- The AI agent compares the implementation against the OpenAPI spec
- Reports any missing endpoints, incorrect data types, or schema mismatches
- Provides guidance on achieving conformance certification

### Validation Checklist
- [ ] All mandatory endpoints implemented
- [ ] Data models match TM Forum schema
- [ ] Error responses follow TMF630 REST API Design Guidelines
- [ ] HATEOAS links included where specified
- [ ] Pagination implemented for collection resources
