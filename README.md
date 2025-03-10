These Matlab scripts code the Method of Characteristic to plot a supersonic Nozzle gemoetry (2D) based on operating conditions with a Logarithmic spacing of the characteristic lines.
The variables taken as input are Me, Gamma and the number of iterations.
The origin of characteristic lines are taken as (0,1) coordinates.

PMF.m script defines the PMF function used in MinLengthNozzle

# README: MinLengthNozzle.m

## Overview
The `MinLengthNozzle.m` script implements the **Method of Characteristics** to design a **minimum-length supersonic nozzle**. It calculates and visualizes the characteristic lines and wall contours necessary to achieve a specified exit Mach number while maintaining smooth flow expansion.

## Requirements
- MATLAB
- The function `PMF.m` (Prandtl-Meyer function), which is required for Mach number and flow angle calculations.

## Function Usage
```matlab
MinLengthNozzle(G, Me, n)
```
### Inputs
- `G`  → Ratio of specific heats (gamma, \( \gamma \))
- `Me` → Desired exit Mach number
- `n`  → Number of characteristic lines used in the method

### Outputs
The script generates:
- The `xwall` and `ywall` variables in the MATLAB workspace, representing the nozzle wall geometry.
- A plot displaying:
  - The **nozzle wall profile**
  - The **characteristic lines**
  - The **expansion and reflection waves**

## Explanation of Key Components
1. **Initialize Variables:**
   - Matrices are created to store values for Mach numbers, flow angles, Mach angles, characteristic lines, and coordinates.
2. **Compute Maximum Expansion Angle:**
   - Uses the Prandtl-Meyer function to determine the maximum expansion angle.
3. **Construct Initial C+ Line:**
   - Determines the first characteristic line starting from the throat.
4. **Compute Characteristic Web:**
   - Iteratively solves for intersection points and flow properties.
5. **Determine Nozzle Wall Contour:**
   - Finds wall coordinates using the last characteristic line.
6. **Plot Nozzle Geometry:**
   - Displays the nozzle shape along with the characteristic lines.

## Notes
- Ensure the function `PMF.m` is available in the MATLAB path.
- The nozzle design assumes inviscid, isentropic flow conditions.
- The grid resolution depends on the number of characteristics (`n`). Increasing `n` improves accuracy but increases computation time.

## Example Usage
```matlab
MinLengthNozzle(1.4, 3, 20)
```
This will generate a minimum-length nozzle for **air (\( \gamma = 1.4 \))**, an **exit Mach number of 3**, using **20 characteristic lines**.

---
**Author:** [Your Name]  
**Date:** [Today's Date]


