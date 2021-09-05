# Schema Registry

## Functions

- Storing and retrieving schema

- Stores a versioned history of all schemas based on a specified subject name strategy, provides multiple compatibility settings and allows evolution of schemas according to the configured compatibility settings and expanded support for these schema types.

## Schema Evolution & Compatibility

- `BACKWARD`: Consumer using schema X can process data produced with schema X or X-1
- `FORWARD`: Data produced using schema X can be read by consumers with schema X or X-1
- `FULL`: `BACKWARD` and `FORWARD` compatibile between schemas X and X-1
- `NONE`: schema compatibility checks are disabled

| Compatibility Type | Changes Allowed | Upgrade First | Check Against which schemas |
|---|---|---|---|
| `BACKWARD` | Delete fields, Add optional fields | Consumers | Last Version |
| `FORWARD` | Add fields, Delete optional fields | Producers | Last Version |
| `FULL` | Add optional fields, Delete optional fields | Any order | Last Version |
| `NONE` | All changes are accepted | Depends | Compatibility checking disabled |

## Avro

