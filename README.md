# Virtual-P1-Sensor-for-Z-HA-Integration

Provides the YAML Code for a virtual P1 which can be used in Z-HA instead the original one.

Content of the virtual P1:
- adjustable Target
- adjustable Deathzone around the Target
  > within the Deathzone,the P1 shows "0"     to increase the amount of regulation      steps
- "Winterbetrieb"
  > adjustable switching threshold. P1         provides only loadings over the           threshold to work only in areas of        good efficency when there is not          enough solar energy
