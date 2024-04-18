# rpi hardware pwm
![CI status](https://github.com/pioreactor/rpi_hardware_pwm/actions/workflows/ci.yaml/badge.svg)
[![PyPI version](https://badge.fury.io/py/rpi-hardware-pwm.svg)](https://badge.fury.io/py/rpi-hardware-pwm)

Access the hardware PWM of a MPU using Linux sysfs with Python. More lightweight than alternatives.

### Installation

1. Setup device tree to expose PWM chip(s) and channel(s)
2. Install this library: `sudo pip3 install rpi-hardware-pwm`



### Examples


> For Rpi 1,2,3,4, use chip=0; For Rpi 5, use chip=2



```python
from rpi_hardware_pwm import HardwarePWM

pwm = HardwarePWM(pwm_channel=0, hz=60, chip=0)
pwm.start(100) # full duty cycle

pwm.change_duty_cycle(50)
pwm.change_frequency(25_000)

pwm.stop()


```

### History

The original code is from [jdimpson/syspwm](https://github.com/jdimpson/syspwm), We've updated it to Python3 and
made it look like the `RPi.GPIO` library's API (but more Pythonic than that.).

