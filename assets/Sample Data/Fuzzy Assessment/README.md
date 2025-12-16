\# Fuzzy Assessment Sample Data



\## Description

This dataset provides sample inputs for the \*\*Fuzzy Assessment\*\* module of the Pavement Analysis Suite.  

It supports multi-criteria pavement performance evaluation using fuzzy AHP–based weighting and deductive aggregation.



The dataset includes section-level distress indicators, normalization rules, expert-derived weights, and the raw survey data used to derive these weights.



---



\## File List



\### 1. ltpp\_data.csv

Section-level pavement condition and distress indicators.



\- Each row represents one pavement section.

\- Each column represents a distress or condition indicator.

\- Values are raw measurements prior to normalization.



Typical indicators include:

\- Roughness  

\- Rutting  

\- Cracking  

\- Potholes  

\- Bleeding  

\- Raveling  

\- Thickness Deficiency  

\- Subsurface Cracking  



---



\### 2. data\_dic.csv

Normalization rules for mapping raw distress values to standardized condition scores.



\- Defines threshold values corresponding to condition scores of 100, 80, 50, 25, and 0.

\- Used to normalize heterogeneous distress indicators to a common 0–100 scale.



---



\### 3. criteria\_weights.csv

Aggregated weights for high-level performance criteria.



\- Derived from expert surveys using fuzzy AHP.

\- Weights represent the relative importance of each criterion.

\- Typical criteria include:

&nbsp; - Safety  

&nbsp; - Rideability  

&nbsp; - User Costs  

&nbsp; - Deterioration Rate  

&nbsp; - Environmental Impact  



---



\### 4. ifpi\_defect\_weights.csv

Defect-to-criterion impact weights used for fuzzy aggregation.



\- Defines the relative contribution of each pavement defect to each performance criterion.

\- Used in the computation of the \*\*Integrated Fuzzy Performance Index (IFPI)\*\*.



---



\### 5. ipdi\_distress\_max\_impact\_survey.csv

Maximum impact values for deductive performance assessment.



\- Survey-based values defining the maximum possible impact of each distress on each criterion.

\- Used in the \*\*Integrated Deductive Performance Index (IDPI)\*\* through sigmoid-based deduction functions.



---



\### 6. Criteria Weights Survey Data.csv

Raw expert survey data for criteria weighting.



\- Contains pairwise or rating-based comparisons between performance criteria.

\- Used to derive `criteria\_weights.csv`.



---



\### 7. Defects Impact-Weights Survey Data.csv

Raw expert survey data for defect impact assessment.



\- Contains expert ratings describing how individual defects affect each performance criterion.

\- Used to derive defect impact weights and maximum impact values.



---



\## Intended Use

The dataset is intended for:

\- Demonstrating fuzzy multi-criteria pavement performance assessment

\- Testing normalization and aggregation workflows

\- Educational and research applications



---



\## Notes

\- This is a demonstration dataset and is not intended to represent network-level pavement conditions.

\- Survey responses are anonymized.

\- Raw survey files are provided for transparency and reproducibility.



---



\## Citation

If this dataset is used in academic or technical work, please cite the associated \*\*Pavement Analysis Suite\*\* and/or the related thesis or publication.



