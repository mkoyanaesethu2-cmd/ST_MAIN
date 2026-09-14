# PredictIQ n8n ingestion and normalization

Approved sources enter source-specific intake workflows. Each workflow creates a source envelope, maps it to the canonical event, performs a minimum validation and returns an acknowledgement. The master flow creates a Vehicle Genome patch and requests SmartQ evaluation for VIN-linked NOK, TREND or REWORK events.

This is a credential-free proof-of-concept structure. Source field names are proposed mappings based on the current PredictIQ demonstration and available stud-welding report field references. Confirm contracts with the owners of MSB, MRS, geometry and Assembly EC before production use.

## Order
1. 01 Part Geometry
2. 02 Geometry Pairing
3. 03 MSB Technical
4. 04 MRS Quality
5. 05 Master orchestration

## Production controls
- Approved interfaces only
- Managed credentials, never stored in workflow exports
- Dead-letter path and replay controls
- Idempotency on event_id
- UTC timestamps and plant-local display conversion
- Schema versioning and source contract tests
- Human approval before action or new SmartQ learning
