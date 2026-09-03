# Healthcare Data Governance and Cleaning

## Objective

Prepare healthcare data responsibly while identifying clinical data-quality risks using reproducible validation rules.

## Dataset

This project uses a small synthetic/de-identified patient dataset containing 10 records.

The dataset includes:

- PatientID
- Age
- Gender
- Diagnosis
- PrimaryMedication
- DosageMg
- TreatmentDurationDays
- Readmitted
- BloodPressure
- CholesterolLevel

## Data Governance

The dataset does not contain direct identifiers such as patient names, addresses, phone numbers, or email addresses.

PatientID values are treated as synthetic identifiers for this training exercise.

This dataset is intended for educational data-quality and governance work and not for clinical decision-making.

## Validation Performed

The following checks were performed:

1. Field and data type validation
2. Missing-value validation
3. Duplicate PatientID validation
4. Age range validation
5. Treatment duration validation
6. Readmission category validation
7. Blood pressure format validation
8. Cholesterol numeric validation
9. Medication dosage numeric validation

## Validation Results

- Total records: 10
- Duplicate PatientIDs: 0
- Missing values: 0
- Invalid ages: 0
- Invalid treatment durations: 0
- Invalid readmission values: 0
- Invalid blood pressure formats: 0
- Invalid cholesterol values: 0
- Invalid dosage values: 0

## Important Data-Quality Observation

The dosage field requires careful interpretation because medication dosage units are medication-specific.

The Levothyroxine record contains 0.05 mg. This value was retained rather than converted because the task requires cleaning without inventing clinical values.

## Deliverables

- `healthcare_patients_cleaned.csv` — validated dataset
- `data_dictionary.md` — field definitions and governance notes
- `validation_notebook.ipynb` — reproducible validation process
- `exception_log.md` — validation exceptions and observations

## Conclusion

The supplied sample passed the basic structural and quality checks. No records required deletion or replacement.

The primary governance observation is the need for clearer medication dosage-unit documentation.
