# MQ137-Sensor
This is a little task to calibrate an amoniac sensor MQ137, using esp8266 module. 

# MQ137-Sensor
This is a little task to calibrate an amoniac sensor MQ137, using esp8266 module. 

First considerate sensor resistor ($R_s$) is in serie with constant resistor ($R_L$).
With a voltage divider We can relate the voltage on constant resitor $V_L$ to $R_s$.
$$ R_s = R_L ({V_c \over V_L}-1) $$

Looking the datasheet grafic of MQ137, the points of the graphs can be noted.
$$ (1, 0.6)  <====>   (X_1 , Y_1) $$
$$ (4, 0.4)  <====>   (X_2 , Y_2) $$
$$ (40, 0.2) <====>   (X_3 , Y_3) $$

With this data we can solve the following equation.
$$ log({R_s \over R_o}) = m*log({PPM})+b$$

to find the slope of the equation.

$$m=[ {  log(y_2) - log(y_1) \over log(x_2)- log(x_1)}] $$
$$m=[ {  log({y_2 \over y_1}) \over log({x_2 \over x_1})}] $$
$$m=[ {  log({0.2 \over 0.6}) \over log({40 \over 1})}] $$
$$m=[ {  -0.4771 \over 1.6}] $$
$$m= {  -0.2981} $$

