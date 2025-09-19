# ebikechargecontroller
An iot device to sit between a dumb battery charger and a battery, allowing one control over charge level, battery level telemetry, etc. written for esphome


## usage
in its default state, the display shows:
-the measured battery voltage
-the estimated battery percentage (based on an estimated linear voltage-SOC relationship from 30v-42v)
-the current target state of charge


additional values exposed to home assistant and the web interface:

-"charge margin" - the charge controller will wait to start charging until percentage drops at least this value bel;ow the target state of charge to begin charging. this is to implement rudimentary hysteresis and avoid rapid cycling
-"bike odometer" - the user is expected to set this value to match their odometer regularly, ideally after each ride

## setting odometer
when the rotary encoder is pressed in, the target state of charge on the display will be replaced by "km", followed by the currently set odometer value.

To set this odometer, while the encoder is pressed in, turn the encoder:
-clockwise to increase the value in increments of 1km
-anticlockwise to increase it in values of 0.1km

the intent of the odometer is to provide a convenient way of inputting the bike's odometer into home assistant for ease of statistical analysis
