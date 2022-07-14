# LMT87
The LMT87 device is a precision CMOS analog temperature sensor with a linear output voltage that is inversely proportional to temperature.

Here is the datasheet for this device: https://www.ti.com/lit/ds/symlink/lmt87.pdf

                MD5                             SHA-1
17f1702e1056186f86021e10f9e8e44c 0d0be8f79b70a96b1b968fea38c75f04f5e643b2 LMT87.pdf


Main TI.com landing for LMT87: https://www.ti.com/product/LMT87



This project was created to help enigneers, technicians, and hobbyist quicky get the LMT87 low voltage temperature sensor working in their own projects.

**The characteristic equations below should make it easy for you to design your own circuits around this device.**


# Basic circuit used to test and gather characteristic data:

![Simple Circuit](<lmt87lpg.png>)


# Characteristic equations:

Equation 1 (for 0 (uA) <= Iout <= 50 (uA):
**Vout = ???? * TemperatureInFahrenheit + ????? * VDD + ?????? * RL + ??????**

The coefficient of determination (r-squared) for this Equation 1 is ???????.

Equation 2 (for -50 (uA) <= Iout <= 0 (uA)):
**Vout = ???? * TemperatureInFahrenheit + ????? * VDD + ?????? * RL + ??????**

The coefficient of determination (r-squared) for Equation 2 is ???????.

**NOTE 1: Iout must be entered into the characteristic equations in uA (microAmps = 1x10^-06 Amps).**
**NOTE 2: From the manufacturer's datasheet, Iout must be:  -50uA <= Iout <= 50uA  for normal temperature sensing operation.**
**NOTE 3: Regarding these characteristic equations and the schematic above, I am defining Iout to be a postiive (+) when Iout is flowing out of the LMT87, and I am defining Iout to be a negative (-) when Iout is flowing into the LMT87,.**

So, for example 1, if VDD is 3.30 Vdc, the ambient temperature is 77.0 degrees Fahrenheit, and RL (your equivalent load resistance) is 100K Ohms, then you would expect Vout to be approximately ????? Volts.

Vout = ????? * (77.0) + ?????? * (3.30) + ????? * (100) + ???????? = ?????

Vout ~ ????? Volts


For example 2, if VDD is 3.30 Vdc, the ambient temperature is 77.0 degrees Fahrenheit, and RL (your equivalent load resistance) is 100K Ohms, then you would expect Vout to be approximately ????? Volts.

Vout = ????? * (77.0) + ?????? * (3.30) + ????? * (100) + ???????? = ?????

Vout ~ ????? Volts



# Notes and limitations of the characteristic equations:

Besides the limitations listed in the [manufacturer's datasheet](lmt87.pdf "lmt87.pdf"), below are the ranges used in my tests to derive the characteristic equation shown above.  I anticipate adding wider temperature ranges to my tests as time and ambient temperatures permit which in turn will produce tweaks to the characteristic equation. However, I expect the characteristic equation above to be good for any situation in or "near" the domain criterion listed below.

76.8 degrees Fahrenheit <= Ambient Temperature <= 91.0 degrees Fahrenheit <br />
AND <br />
3.128 Vdc <= VDD <= 5.260 Vdc <br />
AND <br />
21.51K Ohm <= RL <= 221.6K Ohm

I used 9 different LMT87s to acquire the data. 102 different data points were used to determine the characteristic equation.

# Another good analog temperature sensor:

https://github.com/Joe0x7F/MCP9701A

# Warning:

The TMP35/TMP36/TMP37 is an unpredictable/unstable product. I recommend against ever using it.

See https://github.com/Joe0x7F/TMP36.
