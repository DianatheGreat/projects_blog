---
title: Dehumidification for an Air Quality Monitoring Station
date: 2020-06-16
hero: "/images/KOALAonfence_cropped.jpg"
excerpt: Summary of a year long research project pursuing a low-power, low-const
  dehumidification option to prove dehumidification concept for low-cost
  particulate matter sensors.
timeToRead: 8
authors:
- Diana Simpson

---
The KOALA air quality monitoring stations were developed by Dr. Lidia Morawska with assistance from Dr. Matthew Dunbabin and others (ILAQH, n.d.). The reason a dehumidification unit was being investigated for the KOALA units was due to the inclusion of a low-cost particulate matter sensor. It is the Plantower PMS 1003, which can measure particles from 0.3$\mu$m up to 10$\mu$m. It has been noted in some studies that these sensors experience a non-linear inflation in readings with respect to humidity $>75%$ (Jayaratne et al., 2018).

## The Project

### Initial Research

Multiple passive and active dehumidification options were investigated as potential candidates for testing:
- various forms of desiccant
- thermoelectric modules (TEM)
- fans
- air conditioning
- magnetic air conditioning
- fire
- ice water coils
It was determined that the most viable option to test was the TEM. Looking at the power specifications for various modules, a Marlow RC3-4-01 single-stage thermoelectric module with a $\delta \text{T}_{max}$ of $70^{\circ}$C, a $\text{V}_{max}$ of 4.1Vm an $\text{I}_{max}$ of 3.7A, and a $\text{Q}_{max}$ of 10.3W.

### Designing the experiment

The design of the experiment to prove whether the TEM is a viable dehumidifcation solution for the KOALA proved to be slightly more challenging than anticipated. But, this was primarily due to lack of experience with systems of this nature.

The first design was based off of the standard dehumidification units and some DIY air conditioner designs found online. It was placed halfway through a box, secured with foam to make the box as air-tight as possible. Each iteration was an attempt to reduce and minimise the air volume being processed to better replicated the needs of the Plantower PMS 1003 particulate monitor.

The air volume started at approximately $\frac{3}{4}\text{m}^3$. The second set, still utilising the first dehumidifier design was reduced to 1,350$\text{cm}^3$. The third sets, utilising two new designs for the dehumidifier were further reduced to 620$\text{cm}^3$. With the final experimental design minimised to a mere 4.4$\text{cm}^3$.

All experiments were executed using at least one Arduino Mega 2560, at least one Plantower OMS 1003, at least one BME280 humidity sensor, the TEC unit with accompanying heatsinks, a 5V fan, a 12V power supply with an L298N circuit setup with a 5V output, and a QJE PS3005 power supply. The earlier experiments also used an si7021 humidity sensor, and the latter used either one ACS712 current sensor or two ACS723 (low current) current sensors.

### Results

The experimental outputs continually demonstrated that TEM was an effective unit to dehumidfy the air volume. But, the time and power required were the largest hurdles. With the final design, utilising minimal air volume, it was determined the humidity could be reduced at an optimal rate of -1.24$\frac{\%}{sec}$. With an ideal 20 second timeframe, this would allow for a 24.8% reduction in relative humidity being measured by the sensor. Which allows even an environment with 100% humidity to nearly reach the 75% threshold. This also allowed for the measurement and calculation of power used by the TEM and its accompanying fan. It was determined that a maximum of 0.0231Ah with 9.1V (using 4.1V for the TEM and 5V for the fan).

### Power Research

The initial research pointed towards the utilisation of ultracapacitors as a way to trickle power from the existing KOALA power system, while minimising impact. Allowing the ultracapacitors to supply the short-term power when required. It was also hypothesised that a lower power fan could be advantageous for the circuit.

Using the 0.020289Ah mean as an example:
Since $Q_C = Q_{Ah} \times 3600$, $$Q_C = 0.020289Ah * 3600 = 73.0396C$$
Also since, $1 \frac{C}{V} = 1F$: $$73.0396C \divide 9.1V = 8.0263F$$

It was calculated that obtaining a set of ultracapacitors with a total capcitance of 8.03F at 9.1V would generate the desired power level. Unfortunately, due to time and resource constraints, circuit design and additional testing with potential power solutions was required to be delegated to a separate project.

##### References

ILAQH. Establishing advanced networks for air quality sensing and analysis, n.d. URL: `https://research.qut.edu.au/ilaqh/porjects/koala-sensors/`.

R. Jayaratne, X. Liu, P. Thai, M. Dunbabin, and L. Morawska. The influence of humidity on the performance of low-cos air particle mass sensor and the effect of atmospheric fog. _Atmospheric Measurement Techniques_, 11(8):4884-4890, 2018. URL: `https://www.atoms-meas-tech.net/11/4883/2018/`.
