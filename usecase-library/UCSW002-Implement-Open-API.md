# UCSW002: Implement TM Forum Open API

This use case describes how an **AI agent skill assists developers in implementing a TM Forum Open API** in their target programming language.

It is based on the following assumptions:
- The developer wants to implement a specific TM Forum Open API (e.g., TMF620, TMF629)
- The implementation should conform to the official OpenAPI specification 
- The target language is Python, Node.js, or Rust

**ISSUE: TM Forum Assets are currently only available behind the TMForum 'paywall' in a human-friendly (but not necessarilty Agent friendly) format - this is partly to capture download statistics. This applies to both specs and CTKs.**

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
| Java | Spring Boot | Enterprise-grade REST APIs with rich ecosystem |
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

The implementation should be validated against the TM Forum specification and tested using the official Compliance Test Kit (CTK).

### Validation Steps

1. **Schema Compliance**: Verify generated models match TM Forum JSON Schema
2. **Endpoint Coverage**: Ensure all required endpoints are implemented
3. **Response Format**: Validate response structures against specification
4. **CTK Testing**: Run the official TM Forum Compliance Test Kit against the implementation
5. **Conformance Preparation**: Identify gaps for TM Forum Open API conformance certification

### Compliance Test Kit (CTK)

The TM Forum provides a Compliance Test Kit (CTK) for each Open API to validate implementations against the specification.

#### Downloading the CTK

1. Navigate to the [TM Forum Open API Table](https://tmforum.org/oda/open-apis/table)
2. Locate the target API (e.g., TMF620 Product Catalog Management API)
3. Download the CTK package for the API version you are implementing
4. The CTK typically includes:
   - Test scripts (usually Python-based)
   - Configuration templates
   - Sample test data
   - Documentation for running tests

#### Running the CTK

1. Configure the CTK with your implementation's base URL:
   ```bash
   # Example configuration
   export API_BASE_URL=http://localhost:8080/tmf-api/productCatalogManagement/v4
   ```

2. Install CTK dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Run the test suite:
   ```bash
   python run_ctk.py --api TMF620 --version v4
   ```

4. Review the test report for:
   - Passed/failed test cases
   - Missing mandatory endpoints
   - Schema validation errors
   - Response format issues

#### Interpreting CTK Results

| Result | Action Required |
|--------|-----------------|
| PASS | Endpoint conforms to specification |
| FAIL | Fix implementation to match spec requirements |
| SKIP | Optional endpoint not implemented (acceptable) |
| ERROR | Test configuration or connectivity issue |

### How to
- The AI agent assists in downloading and configuring the CTK for the target API
- Guides the developer through running the test suite
- Analyzes CTK output and suggests fixes for failing tests
- Reports any missing endpoints, incorrect data types, or schema mismatches
- Provides guidance on achieving conformance certification

### Validation Checklist
- [ ] All mandatory endpoints implemented
- [ ] Data models match TM Forum schema
- [ ] Error responses follow TMF630 REST API Design Guidelines
- [ ] HATEOAS links included where specified
- [ ] Pagination implemented for collection resources
- [ ] CTK test suite passes for all mandatory tests
- [ ] Ready for formal TM Forum conformance certification submission
