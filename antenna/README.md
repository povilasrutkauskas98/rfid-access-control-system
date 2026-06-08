The antenna was designed using STMicroelectronics' eDesignSuite tool. Based on the required inductance value, the tool generated the antenna geometry dimensions for operation at 13.56 MHz.

The inductance was calculated using the internal tuning capacitor of the ST25TV tag, which has a capacitance of 99.7 pF. The resonant frequency of the system is determined by:

<img width="98" height="45" alt="image" src="https://github.com/user-attachments/assets/e46c6dd6-1422-4a44-b474-2b13108c9816" />



Rearranging the equation to solve for inductance:

<img width="128" height="48" alt="image" src="https://github.com/user-attachments/assets/35d359c1-a590-476a-aae7-96e25f20897c" />


Using:

C = 99.7 pF
f = 13.56 MHz

the calculated inductance is:

L = 1.38 µH

This inductance value was used as the design target for both reader and tag antennas.

Reader Antenna
Dimensions: 20 mm × 20 mm
Trace width: 0.40 mm
Trace spacing: 0.41 mm
Tag Antenna
Dimensions: 15 mm × 15 mm
Trace width: 0.22 mm
Trace spacing: 0.30 mm

Both antennas were fabricated on standard PCB material using 35 µm copper thickness.

The antenna was successfully tuned to 13.56 MHz and validated using ST25R3911 and ST25TV devices.
