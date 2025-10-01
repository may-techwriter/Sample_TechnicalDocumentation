# API_Documentation

This folder contains the OpenAPI specification and supporting files for the biometric web service **FaceRecognition**, which enables secure identity registration and facial recognition-based identification.

## Contents

- `FaceRecognition_RESTAPI.yaml`: OpenAPI 3.0 specification defining all available endpoints and expected behavior.
- *(Optional)* Endpoint-specific `.md` files may be added in future iterations if narrative or audience-specific documentation is needed.

## How to Use

- View the OpenAPI spec using [Redoc](https://redocly.github.io/redoc/?url=https://raw.githubusercontent.com/may-techwriter/Sample_TechnicalDocumentation/main/API_documentation/FaceRecognition_RESTAPI.yaml) for static documentation.
- For interactive exploration, upload the YAML file to [Swagger Editor](https://editor.swagger.io/).
- Validation examples using Postman and cURL are available in the `Validation/` folder.

## Notes

- All endpoints are defined in a single YAML file (`FaceRecognition_RESTAPI.yaml`) and grouped by operation.
- The API supports full CRUD (Create, Retrieve, Update, Delete) operations for biometric identities stored in PostgreSQL or Microsoft SQL Server.
- No OCR functionality is included in this implementation.
- This documentation is static and not connected to a live backend service.

## Glossary

For definitions of key terms used in the API (e.g., `group`, `vector`, `score`, `matchName`), see the [Glossary](../Glossary/Glossary.md).