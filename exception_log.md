# Exception Log — Healthcare Data Governance and Cleaning

## Purpose

This exception log records data-quality observations identified during validation of the synthetic/de-identified patient dataset.

The log follows a conservative approach: clinical values are not invented, guessed, or changed without an explicit and unambiguous rule.

## Validation Exceptions and Observations

| ID     | Field                 | Record      | Observation                                                      | Action Taken                        | Reason                                                                           |
| ------ | --------------------- | ----------- | ---------------------------------------------------------------- | ----------------------------------- | -------------------------------------------------------------------------------- |
| EX-001 | DosageMg              | PAT-210     | Levothyroxine dosage is recorded as `0.05 mg`                    | Retained as supplied and documented | Dosage interpretation is medication-specific and no conversion rule was provided |
| EX-002 | PatientID             | All records | Duplicate PatientIDs were checked                                | No action required                  | All 10 PatientIDs were unique                                                    |
| EX-003 | Missing values        | All records | Missing-value check performed                                    | No action required                  | No missing values were identified                                                |
| EX-004 | Age                   | All records | Age values checked for numeric type and reasonable range         | No action required                  | No invalid age values were identified                                            |
| EX-005 | TreatmentDurationDays | All records | Treatment duration checked for positive numeric values           | No action required                  | No invalid treatment durations were identified                                   |
| EX-006 | Readmitted            | All records | Readmission values checked against `Yes`/`No`                    | No action required                  | No invalid categories were identified                                            |
| EX-007 | BloodPressure         | All records | Blood pressure values checked for `systolic/diastolic` structure | No action required                  | No invalid formats were identified                                               |
| EX-008 | CholesterolLevel      | All records | Cholesterol values checked for numeric type                      | No action required                  | No invalid numeric values were identified                                        |

## Summary

* Total records reviewed: 10
* Confirmed duplicate PatientIDs: 0
* Missing values identified: 0
* Invalid age values: 0
* Invalid treatment durations: 0
* Invalid readmission values: 0
* Invalid blood pressure formats: 0
* Invalid cholesterol values: 0
* Invalid dosage values based on the defined structural validation: 0
* Clinical values deleted or replaced: 0

## Cleaning Decision

No patient records were deleted.

No clinical values were replaced with guessed or estimated values.

The Levothyroxine dosage of `0.05 mg` was retained because the supplied task does not provide sufficient information to justify changing or converting the value. It is documented as a data-quality observation for further review rather than treated as a confirmed clinical error.

## Governance Note

An exception does not necessarily mean that a value is clinically wrong. Exceptions may identify values requiring additional context, documentation, or domain review.

This exercise is for data-quality and governance training and does not provide clinical advice or establish medical correctness.
