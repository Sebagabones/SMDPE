# 1.0 General Goals
To develop an automated and extensible scoring system that processes diet recall data and measures plastic exposure level in order to replace the current manual matrix scoring method.

# 2.0 Current System
Currently, the diet recall data is manually scored using a matrix that was developed in a previous study phase. The matrix assesses plastic chemical exposure in each meal as the sum of the active binary indicators, which are assigned to food properties associated with plastic chemical exposure.
The process is labor-intensive, prone to error and it isn't scalable.

# 3.0 Proposed System
## 3.1 Overview
The proposed system is an automated scoring system that
- Takes a CSV of diet recall data exported from REDCap
- Replicates and improves on the existing scoring matrix logic
- Measures each participant's plastic exposure per eating occasion
- Outputs scores in a structured CSV
- The system will be maintainable and extensible for future study phases

## 3.2 Functional Requirements
- Accept diet recall CSV files
- Extract food preperation and storage factors from data
- Match food codes to properties associated with plastic chemical leaching
- Replicate existing scoring matrix logic
- Support more granular scoring based on additional food/ preparation attributes
- Apply weighting based on food volume/ likelihood of exposure
- Generate a detailed and summary CSV output
- Handle missing or unknown values gracefully
- Handle incorrect input format gracefully

## 3.3 Nonfunctional Requirements
### 3.3.1 User Interface and Human Factors
- Users will include dietitians and researchers
- No GUI is required (input/output will be CSVs)
- Will use a simple command-line interface
- Minimal training needed if documentation is clear

### 3.3.2 Documentation
- User guide (for the dietitians) explaining how to use the code. Will include input format, runnning it and interpreting the output
- Documentation explaining scoring logic
- Inline code comments and README for repository

### 3.3.3 Hardware Consideration
- Will be run on standard personal computers used in research settings
- No specialized hardware

### 3.3.4 Performance Characteristics
- Output latency should be less than 5 seconds
- Each diet recall can have up to 15 meals with up to 75 items each

### 3.3.5 Error Handling and Extreme Conditions
- Log warnings for missing fields or inconsistencies
- Validate formats before processing to avoid exceptions

###3.3.6 System Interfacing
- Input: CSV files exported from REDCap
- Output: CSV files summarizing plastic exposure after each meal and the total
- Output file should have no special characters and be numeric only

### 3.3.7 Quality Issues
- Scores should always positive
- Should not corrupt data/ crash if there is bad input
- Should include automated test cases for scoring logic

### 3.3.8 System Modifications
- Future versions may incorporate more nuanced exposure models
- Support for new REDCap data formats or additional metadata may be required.
- Scoring rules may be updated based on future scientific findings.

### 3.3.9 Physical Environment
- System will be used in a standard computing environment by research staff

### 3.3.10 Security Issues
- Must comply with NDA and data sensitivity requirements.
- No raw participant identifiers should be stored in outputs.
- Source code is to remain closed and protected via private repository access.

## 3.4 Constraints
- Must be completed within a single university semester
- Code must be robust and maintainable
- Data access is restricted
- All development must respect confidentiality and IP agreements
- Code must be closed source and not publicly distributed
