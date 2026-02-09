# Virtual-P1-Sensor-for-Z-HA-Integration

Provides the YAML Code for a virtual P1 which can be used in Z-HA instead the original one.

Content of the virtual P1:
- adjustable Target
- adjustable Deathzone around the Target
  > within the Deathzone,the P1 shows "0"     to decrease the amount of regulation      steps
- "Winterbetrieb"
  > adjustable switching threshold. P1         provides only loadings over the           threshold to work only in areas of        good efficency when there is not          enough solar energy
- set min SoC to 50% while standby, to avoid the 25W discharge in idle mode

- Helpers needed:
  
  - input_number.zendure_p1_last_setpoint
   (P1 output, have to be insert in Z-HA P1)
  - input_boolean.zendure_winterbetrieb
   (enable/disable "Winterbetrieb")
  - input_number.p1_sensor_target
   (set sensor target)
  - input_number.p1_sensor_deathband
   (set Deathband to +-input_number)
  - input_number.zendure_change_threshold_w
   (set switching target)
  - input_number.p1_schwellwert_winterbetrieb
   (set switching threshold for Winterbetrieb)
  - input_datetime.gesamt_soc_min_hold_until
   (needed for hysteresis till Winterbetrieb)

- Sensors:
  - sensor.shellypro3em_total_active_power (original P1 Sensor; - Electricity feed-in, + grid purchasing)
  - sensor.gesamt_kombisensor_laden_entladen (Sensor which show charging/discharging of the whole Zendure System; - charging, + discharging)
  - min SoC entity (it`s input_number.gesamt_soc_min in code, could be also minSoC entity)
  - number.l2_solarflow_2400_ac_output_limit (Output limit entity, for set current output to zero when "Winterbetrieb" is started)
  - number.l3_solarflow_2400_ac_output_limit (Output limit entity, for set current output to zero when "Winterbetrieb" is started; if you have only one device, you need only one outputlimit entity)

  

