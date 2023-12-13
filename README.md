YAML I used in ESPHOME to have my esp controller become a stand-alone controller to reduce the overshoot after a start or restart after defrosting of the heat pump.
Only works when the heat pump is set to HEAT, WATER only.
The 'stooklijn' or heating curve can be set either via the esp webinterface or via Home Assistant, and will replace the heating curve in your RMC. So simply copy the values. 

<img width="387" alt="Scherm­afbeelding 2023-12-10 om 11 21 10" src="https://github.com/paqpaqpaq/ThermaV_overshoot_logic/assets/34166264/edeedbe9-aac6-4560-94ad-9611a08b5207">

Simultaneously you can apply an offset to the heating curve as desired.

The logic functions by 'pulling down' the water heating target by 4 degrees for set intervals. 
The needed intervals will depend on the heat pump, water target and overall system, so play around with this. 
There are 5 States in the logic, States 0-4. 'State 1' contains the first delay interval; 'State 2' the second interval and so on.

Make sure the target from States 0-3 remains below the temperature of the outlet water, otherwise the functionality of the logic might be pointless. 

<img width="1079" alt="Scherm­afbeelding 2023-12-08 om 08 15 01" src="https://github.com/paqpaqpaq/ThermaV_overshoot_logic/assets/34166264/a93c1ad8-76d0-4f04-b4b0-3e341c341b8a">

"Stooklijn" must be set to ON for "Overshoot control" to be functional. 
