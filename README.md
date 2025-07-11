# Ansys-Mechanical-CubeSat-Analysis---APDL
This repository will hopefully help those interested in modeling the thermal environment onboard a cube satellite.


# Thermal Analysis Details

This APDL script models the thermal environment of a CubeSat, either in a fixed orientation relative to the Sun or rotating about a single axis. Setting a value to the angular velocity variable, w, will prescribe a rotation in deg/s about the user defined axis of rotation. The axis of rotation is defined through the selection of faces to be subjected to flux through the IF/ELSEIF rotation conditions.

## How to: Setup and Run Simulation

- Outside APDL script:
  1. Import a geometry file into Ansys Mechanical.
  2. Create named selections for the faces to be subjected to solar flux.
  3. Select the 'Transient Thermal' analysis method.
  4. Insert a 'Radiation' condition into the Transient Thermal branch.  <----- More Radiation conditions can be created for faces of differing emissivity, e.g., internal satellite surfaces.
  5. Select the faces/geometries (all external faces if computationally feasible; most accurate representation) to be radiating heat out to vacuum.
  6. Select 'To Ambient'.
  7. Adjust the emissivity value to match that of the selected surface's material.
  8. Set ambient temperature to represent that of free space (roughly 3K, -270.15C)
  9. Insert 'Commands' into the Transient Thermal tab so that the APDL script can be pasted and used.

- Inside APDL script:
  1. Paste the provided APDL script into the 'Commands' window.
  2. Edit any callouts of named selections (Face1,Face2,...) if different notation is used.
  3. Ensure that your desired roll direction/axis is satisfied by the correct assignment of named selections to the IF/ELSEIF conditions.

- Run Script:
  1. Outside of APDL script, click 'solve'.
  2. Monitor results through clicking the 'Solution Information' folder found in the 'Solution' folder.
  3. Insert a 'Temperature Plot Tracker' into the 'Solution Information' folder and right click the tracker to select the 'Switch to Automatic Mode' for the temperature contour plots on your model to be visible through         each iteration.

## Example Cases

The initial tests shown below were to demonstrate the performance of various thermal coatings to be applied to the outer faces of the CubeSat. All coatings and their absorbtivity(α)/emissivity(ε) were defined within this NASA site: https://www.nasa.gov/smallsat-institute/sst-soa/thermal-control/#7.2.1

The case below follows these parameters:
- Time=200s, w=0 deg/s
- α=0.15, ε=0.91 ('AZ-93 White Thermal Control' surface coating)

![image](https://github.com/user-attachments/assets/271a26e8-ecac-4d1e-ac43-1513d26898d4)

The case below follows these parameters:
- Time=200s, w=0 deg/s
- α =0.27,ε=0.88 ('White Silicone Paint PCBE')

![image](https://github.com/user-attachments/assets/ba66cdf8-3a1e-43a5-a995-27ac4c001a3e)

The case below follows these parameters:
- Time=200s, w=1 deg/s
- α =0.27,ε=0.88 ('White Silicone Paint PCBE')

![image](https://github.com/user-attachments/assets/96bdb219-325c-4dcd-8b69-b98c3c76b627)


Each of the cases above began with the solar flux being applied to the x+ face. The simulated clockwise roll of the CubeSat seen above is done by creating named selections of the CubeSats faces:
- "Face1" (x+ Face)
- "Face2" (y+ Face)
- "Face3" (x- Face)
- "Face4" (y- Face)

