# Healthcare Patient Dataset — Data Dictionary

## Dataset Overview

This dataset contains 10 synthetic/de-identified patient records intended for
healthcare data governance and data-quality training.

No direct personal identifiers such as patient names, addresses, phone numbers,
email addresses, or dates of birth are included.

The PatientID values are synthetic identifiers used only to distinguish records.

## Field Definitions

| Field | Data Type | Description | Validation Rule |
|---|---|---|---|
| PatientID | String | Synthetic patient identifier | Required and unique |
| Age | Integer | Patient age in years | Required; positive integer; reasonable range |
| Gender | Categorical | Recorded gender category | Required |
| Diagnosis | Categorical | Recorded diagnosis | Required |
| PrimaryMedication | Categorical | Primary medication | Required |
| DosageMg | Numeric | Medication dosage recorded in mg | Required; numeric; non-negative |
| TreatmentDurationDays | Integer | Treatment duration in days | Required; positive integer |
| Readmitted | Categorical | Whether patient was readmitted | Required; Yes/No |
| BloodPressure | String | Blood pressure in systolic/diastolic format | Required; valid ###/## format |
| CholesterolLevel | Numeric | Recorded cholesterol level | Required; numeric; non-negative |

## De-identification Assessment

The sample is considered de-identified for this training exercise because it
does not contain names, addresses, phone numbers, email addresses, or other
direct personal identifiers.

The PatientID values appear to function as synthetic record identifiers rather
than real-world identifying information.

## Governance Notes

- The dataset should not be used for clinical decision-making.
- No clinical values were invented during cleaning.
- Medication dosage units should be interpreted carefully because dosage
  conventions can vary by medication.
- The Levothyroxine value of 0.05 mg was retained as supplied.
- Dosage values should not be converted without an explicit, documented unit
  conversion rule.

## Data Quality Approach

The dataset was checked for:

1. Missing values
2. Duplicate patient identifiers
3. Invalid data types
4. Invalid age values
5. Invalid treatment durations
6. Invalid Readmitted categories
7. Invalid blood pressure formats
8. Invalid cholesterol values
9. Invalid dosage values
