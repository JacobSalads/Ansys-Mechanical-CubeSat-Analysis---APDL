# Ansys-Mechanical-CubeSat-Analysis---APDL
This repository will hopefully help those interested in modeling the thermal environment onboard a cube satellite.


%%% Thermal Analysis Details %%%

This APDL script models the thermal environment of a CubeSat, either in a fixed orientation relative to the Sun or rotating about a single axis. Setting a value to the angular velocity variable, w, will prescribe a rotation in deg/s about the user defined axis of rotation. The axis of rotation is defined through the selection of faces to be subjected to flux through the IF/ELSEIF rotation conditions. 

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





