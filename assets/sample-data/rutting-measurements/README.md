\# Rutting Measurements Sample Data (AMES TPS)



\## Overview

This sample dataset contains pavement transverse profile measurements

collected using an AMES Transverse Profiling System (TPS). The data are

provided to demonstrate rutting measurement and processing workflows

implemented in the Pavement Analysis Suite.



Transverse surface profiles were acquired at a spatial resolution of

\*\*12 mm\*\* across the pavement width. The dataset includes raw sensor

outputs (intensity and range grids) as well as processed lane-edge

information used to define the valid analysis region.



---



\## Data Collection System

\- \*\*Measurement System:\*\* AMES Transverse Profiling System (TPS)

\- \*\*Profile Type:\*\* Transverse pavement surface profiles

\- \*\*Transverse Sampling Resolution:\*\* 12 mm

\- \*\*Output Representation:\*\* Gridded profile arrays



---



\## Dataset Contents



\### 1) Intensity Grid

\*\*File:\*\* `SampleData\_Intensity\_Grid\_Lane.npz`  

\*\*Format:\*\* NumPy `.npz` (compressed)  

\*\*Key:\*\* `intensity\_grid`  

\*\*Array shape:\*\* `(4166, 4096)`  

\*\*Data type:\*\* `float32`  

\*\*Value range:\*\* 0 – 956  



\*\*Description:\*\*  

Returned signal intensity values recorded by the TPS sensor for each

transverse profile point. Intensity data are primarily used for quality

control, surface texture interpretation, and validation of profile

reconstruction.



---



\### 2) Range Grid

\*\*File:\*\* `SampleData\_Range\_Grid\_Lane.npz`  

\*\*Format:\*\* NumPy `.npz` (compressed)  

\*\*Key:\*\* `range\_grid` \*(stored key name)\*  

\*\*Array shape:\*\* `(4166, 4096)`  

\*\*Data type:\*\* `float32`  

\*\*Value range:\*\* 0 – 306.1  



\*\*Description:\*\*  

Range (distance-to-surface) measurements obtained from the TPS sensor.

These data are used to reconstruct the transverse pavement surface

geometry and serve as the primary input for rut depth computation.



> \*\*Note:\*\* Although the internal NPZ key is named `intensity\_grid`,

the file stores \*\*range values\*\*. The key name is preserved for backward

compatibility and may be updated in future releases.



---



\### 3) Processed Lane Edge Data

\*\*File:\*\* `SampleData\_Lane\_Edge.npy`  

\*\*Format:\*\* NumPy `.npy`  

\*\*Data type:\*\* Object array (dictionary; requires `allow\_pickle=True`)  



\*\*Structure:\*\*  

The file contains a Python dictionary with the following keys:

\- `left`: left lane edge indices

\- `right`: right lane edge indices



Each lane edge defines the valid transverse bounds of the traffic lane

for rutting analysis and is used to exclude shoulder and non-lane areas

from processing.



---



\## Data Organization

The intensity and range grids are stored as two-dimensional arrays:

\- \*\*Rows (4166):\*\* consecutive transverse profile scans along the

&nbsp; longitudinal direction

\- \*\*Columns (4096):\*\* transverse sampling points across the pavement

&nbsp; width (12 mm spacing)



Lane edge data provide the transverse indices corresponding to the

left and right boundaries of the lane for masking and analysis.



---



\## Intended Use

This dataset is intended for:

\- Demonstrating transverse profile reconstruction

\- Rut depth computation and visualization

\- Lane masking using processed lane edges

\- Educational and research demonstrations of pavement rutting analysis



---



\## Limitations

\- The dataset represents a limited sample for demonstration purposes.

\- It is not intended to be statistically representative of

&nbsp; network-level pavement conditions.

\- Absolute calibration parameters and site metadata are not included.



---



\## Usage Example (Python)



```python

import numpy as np



\# Load intensity and range grids

I = np.load("SampleData\_Intensity\_Grid\_Lane.npz")\["intensity\_grid"]

R = np.load("SampleData\_Range\_Grid\_Lane.npz")\["range\_grid"] 



\# Load lane edge data

lane\_edge = np.load("SampleData\_Lane\_Edge.npy", allow\_pickle=True).item()

left\_edge = lane\_edge\["left"]

right\_edge = lane\_edge\["right"]



print(I.shape, R.shape)



