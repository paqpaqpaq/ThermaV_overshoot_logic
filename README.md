YAML I used in ESPHOME to have my esp controller become a stand-alone controller to reduce the overshoot after a start or restart after defrosting of the heat pump.
Only works when the heat pump is set to HEAT, WATER only.
The 'stooklijn' or heating curve can be set either via the esp webinterface or via Home Assistant, and will replace the heating curve in your RMC. So simply copy the values. 

<img width="387" alt="Scherm­afbeelding 2023-12-10 om 11 21 10" src="https://github.com/paqpaqpaq/ThermaV_overshoot_logic/assets/34166264/edeedbe9-aac6-4560-94ad-9611a08b5207">

The logic functions by 'pulling down' the water heating target by 4 degrees for set intervals. 
The needed intervals will depend on the heat pump, water target and overall system, so play around with this. 
There are 5 cases in the logic, cases 0-4. Case 0 contains the first delay interval; case 1 the second interval and so on.

Make sure the target is below the temperature of the outlet water, otherwise the funtionality of the logic might be useless. 

<img width="1079" alt="Scherm­afbeelding 2023-12-08 om 08 15 01" src="https://github.com/paqpaqpaq/ThermaV_overshoot_logic/assets/34166264/a93c1ad8-76d0-4f04-b4b0-3e341c341b8a">
