# Data Dictionary — Healthcare Patient Records

## Purpose

This data dictionary describes the fields in the supplied synthetic/de-identified healthcare patient dataset. It documents each field's meaning, classification, expected data type, validation rule, and privacy/governance considerations.

| Field                 | Description                                   | Classification       | Data Type   | Validation Rule                                                              | Governance / Privacy Note                                                            |
| --------------------- | --------------------------------------------- | -------------------- | ----------- | ---------------------------------------------------------------------------- | ------------------------------------------------------------------------------------ |
| PatientID             | Unique identifier assigned to each record     | Synthetic Identifier | Text        | Must follow the `PAT-###` format and should not be duplicated                | Synthetic/pseudonymous identifier; not a direct identifier such as a name or address |
| Age                   | Patient age in years                          | Demographic          | Integer     | Must be numeric and within a reasonable patient age range                    | Demographic information; should be handled as healthcare-related data                |
| Gender                | Recorded gender category                      | Demographic          | Categorical | Must contain an accepted category and must not be blank                      | Demographic information                                                              |
| Diagnosis             | Primary diagnosis recorded for the patient    | Clinical             | Text        | Must not be blank; values are retained as supplied                           | Clinical information; no diagnosis was invented or changed                           |
| PrimaryMedication     | Main medication recorded for the patient      | Medication           | Text        | Must not be blank                                                            | Medication information; values are retained as supplied                              |
| DosageMg              | Medication dosage recorded in milligrams      | Medication/Treatment | Numeric     | Must be numeric and positive                                                 | Dosage units are medication-specific; values were not clinically reinterpreted       |
| TreatmentDurationDays | Duration of treatment in days                 | Treatment            | Integer     | Must be a positive whole number                                              | Treatment information; no duration was invented                                      |
| Readmitted            | Indicates whether the patient was readmitted  | Outcome/Utilization  | Categorical | Must contain `Yes` or `No`                                                   | Used as an operational outcome field; does not establish clinical causation          |
| BloodPressure         | Blood pressure recorded as systolic/diastolic | Clinical Measurement | Text        | Must follow the expected `systolic/diastolic` format with numeric components | Clinical measurement; values were not modified based on medical assumptions          |
| CholesterolLevel      | Recorded cholesterol measurement              | Clinical Measurement | Numeric     | Must be numeric and checked for invalid values                               | Clinical measurement; no value was imputed or invented                               |

## De-identification Notes

The supplied dataset is identified as synthetic and de-identified training data.

It does not contain direct identifiers such as:

* Patient name
* Home address
* Telephone number
* Email address
* Date of birth

The `PatientID` values are synthetic identifiers used to distinguish records in the exercise. They should be treated as pseudonymous identifiers rather than assuming the records are completely anonymous.

## Data Quality Approach

The dataset was evaluated for:

* Data type consistency
* Missing values
* Duplicate PatientIDs
* Reasonable age values
* Positive treatment durations
* Valid `Yes/No` readmission values
* Blood pressure structure
* Numeric cholesterol values
* Numeric medication dosage values

## Cleaning Principle

Clinical values were not invented, guessed, or changed without an explicit and unambiguous validation rule.

Where a value may require clinical interpretation, the value was retained and documented as a data-quality observation rather than being changed based on assumptions.

## Important Dosage Observation

The Levothyroxine record contains a dosage value of `0.05 mg`.

This value was retained because medication dosage interpretation is medication-specific and the exercise does not provide a rule authorizing conversion or correction. The issue is therefore documented as a governance/data-quality observation rather than treated as a confirmed clinical error.
