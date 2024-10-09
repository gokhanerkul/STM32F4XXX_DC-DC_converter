<h1 align="center">STM32F401RE Full Bridge DC-DC Converter Project</h1>

# _Information_


In this project, an STM32 microcontroller is utilized to control a DC-DC converter, aiming to regulate the output voltage by implementing a Proportional-Integral-Derivative (PID) control algorithm. The input voltage is 12V, and the output voltage is adjustable between 11.56V and 50V. The output voltage is scaled down using a voltage divider (0.756V to 3.3V) to be suitable for the STM32's Analog-to-Digital Converter (ADC).

The feedback voltage from the converter's output is continuously monitored by the ADC and compared to a defined setpoint in the code. The PID algorithm then adjusts the Pulse Width Modulation (PWM) duty cycle to maintain the desired output voltage. Instead of using potentiometers to adjust the setpoint and control parameters, these values are now predefined in the code, allowing for precise and stable control of the system. The STM32's Direct Memory Access (DMA) feature is used for fast and efficient ADC readings, which minimizes CPU overhead and enhances real-time performance in regulating the converter.

This approach showcases the STM32's capability in advanced control tasks, with the PID algorithm ensuring optimal regulation by dynamically adjusting the PWM output based on error correction, offering improved stability and response in power management applications.


## Features

- **PID Control Algorithm:** Implements a Proportional-Integral-Derivative (PID) algorithm for precise output voltage regulation by dynamically adjusting the PWM duty cycle.
- **Setpoint Defined in Code:** The setpoint and control parameters (Kp, Ki, Kd) are predefined in the code, eliminating the need for external potentiometers, offering more stability and ease of tuning.
- **12V Input with Adjustable Output Voltage:** The converter regulates an output voltage ranging from 11.56V to 50V from a 12V input supply.
- **Analog Feedback Monitoring:** Uses an Analog-to-Digital Converter (ADC) to continuously monitor the scaled-down feedback voltage, ensuring accurate control.
- **PWM Control:** A high-frequency Pulse Width Modulation (PWM) signal is generated to drive the DC-DC converter, with a duty cycle range of 0 to 479 (minimum to maximum).
- **Voltage Divider Circuit:** A voltage divider with 47kΩ and 3.3kΩ resistors scales the output voltage to a range suitable for ADC input (0.756V to 3.3V).
- **Direct Memory Access (DMA) for ADC:** The project uses DMA for continuous ADC readings, reducing CPU load and enabling real-time feedback and control.
- **High-Frequency Operation:** The system operates at a 100kHz PWM signal frequency, which is crucial for efficient power conversion.
- **Scalable and Flexible Design:** The design is flexible for future modifications, including changing setpoint values or adjusting PID parameters directly in the code.
- **STM32 Microcontroller:** Takes advantage of the STM32's peripherals, including ADC, PWM, DMA, and general-purpose timers, to achieve efficient and responsive control.



## How can I change my setpoint?

To modify the setpoint dynamically in your STM32 code, you can change the #define PID_SETPOINT 400 to a variable that can be updated during runtime. This way, you can adjust the setpoint as needed.

```sh
#define PID_SETPOINT 400 //setpoint
```
This set point is 10-bit (so can be change between of 0-1024). You can change set point for your systems requirements.

## PID values


You can simply update the values of Kp, Ki, and Kd directly in the code where they are defined as #define constants. This approach is static and doesn't allow real-time tuning unless you reflash the code. For example:

```sh
#define Kp 0.1f
#define Ki 0.0008f
#define Kd 0.015f 
```
Increase or decrease this values for proportional, integral, derrivative gains.
These values may vary from system to system.

## Author: Gökhan Erkul

**Have a good work!**



   [dill]: <https://github.com/joemccann/dillinger>
   [git-repo-url]: <https://github.com/joemccann/dillinger.git>
   [john gruber]: <http://daringfireball.net>
   [df1]: <http://daringfireball.net/projects/markdown/>
   [markdown-it]: <https://github.com/markdown-it/markdown-it>
   [Ace Editor]: <http://ace.ajax.org>
   [node.js]: <http://nodejs.org>
   [Twitter Bootstrap]: <http://twitter.github.com/bootstrap/>
   [jQuery]: <http://jquery.com>
   [@tjholowaychuk]: <http://twitter.com/tjholowaychuk>
   [express]: <http://expressjs.com>
   [AngularJS]: <http://angularjs.org>
   [Gulp]: <http://gulpjs.com>

   [PlDb]: <https://github.com/joemccann/dillinger/tree/master/plugins/dropbox/README.md>
   [PlGh]: <https://github.com/joemccann/dillinger/tree/master/plugins/github/README.md>
   [PlGd]: <https://github.com/joemccann/dillinger/tree/master/plugins/googledrive/README.md>
   [PlOd]: <https://github.com/joemccann/dillinger/tree/master/plugins/onedrive/README.md>
   [PlMe]: <https://github.com/joemccann/dillinger/tree/master/plugins/medium/README.md>
   [PlGa]: <https://github.com/RahulHP/dillinger/blob/master/plugins/googleanalytics/README.md>

