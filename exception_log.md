# Exception Log

## Validation Summary

| Check | Result | Action |
|---|---:|---|
| Duplicate PatientID | 0 found | No changes required |
| Missing values | 0 found | No changes required |
| Invalid Age | 0 found | No changes required |
| Invalid TreatmentDurationDays | 0 found | No changes required |
| Invalid Readmitted value | 0 found | No changes required |
| Invalid BloodPressure format | 0 found | No changes required |
| Invalid CholesterolLevel | 0 found | No changes required |
| Invalid DosageMg | 0 found | No changes required |

## Governance Observation

### Medication Dosage Unit

The `DosageMg` column records medication dosage in milligrams. Medication
dosages are medication-specific, so the unit and interpretation should remain
explicit.

The Levothyroxine record contains `0.05 mg`. This value was retained exactly
as supplied because changing it to another number could introduce an
unsupported clinical transformation.

### Recommended Improvement

For a production healthcare dataset, medication dosage should have a clearly
documented unit and, ideally, a medication-specific dosage standard.

## Cleaning Principle

No clinical values were invented, estimated, or replaced.

Cleaning was limited to validation, documentation, and identification of
potential data-quality and governance risks.

## Final Status

The supplied dataset passed the basic validation checks.

No records required deletion or replacement.
