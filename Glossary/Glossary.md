# Glossary – FaceRecognition API

This glossary defines key terms used throughout the FaceRecognition REST API. These terms reflect the internal logic and naming conventions of the original implementation.

---

## Core Concepts

- **group**: A logical container or category used to organize identities. Examples: `employees`, `students`. Required in most endpoints.

- **name**: The identifier assigned to an individual within a group. It may represent a username, alias, or personal label. Used for enrollment and identification.

- **vector**: The biometric template generated from a facial image. It is linked to a `name` and stored in the database for future matching.

- **vector-name**: The association between a biometric vector and a `name` within a group. Created during enrollment.

- **image**: A facial image submitted for enrollment or identification. Accepted formats include BMP, HEIC, JPG/JPEG, PNG, TIF/TIFF. Must be sent in the request header.

---

## Request Parameters

- **group (path)**: Specifies the group context for the operation. Required in most endpoints.

- **name (path)**: Specifies the identity to be retrieved, updated, or deleted.

- **update (query)**: New identifier to replace an existing `name` or `group`.

- **image (header)**: Binary image data used for biometric processing.

---

## Response Fields

- **timestamp**: Date of the operation in `YYYYMMDD` format.

- **vectorID**: Internal ID of the biometric template.

- **nameID**: Identifier of the enrolled or matched individual.

- **groupID**: Identifier of the group involved in the operation.

- **matchName**: Name of the individual matched during identification.

- **score**: Matching confidence score (0–100). A threshold must be applied to determine if it qualifies as a match.

- **match_found**: Boolean flag indicating whether a match was found (used in some implementations).

- **created**: Date when the identity or group was created.

- **newName / newGroup**: Updated identifiers after a successful modification.

- **missingField**: Indicates which required field was missing in a failed request.

---

## Notes

- Matching operations require a confidence threshold to determine success.
- Some fields (e.g., `match_found`) may be implementation-specific and not present in all responses.
- The API is designed to support full CRUD operations for both `name` and `group` entities.