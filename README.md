# C Library for controlling an MCP3424

Linux userspace I2C module for the MCP3424 ADC. Code was originally ported from the code found [here](https://github.com/abelectronicsuk/ABElectronics_Python3_Libraries/tree/master/ADCPi). This has been used with ABElectronics' ADC Pi and ADC Pi Plus. See [main.c](main.c) for an example of how to use the module.


## Dependencies

This module depends on `libi2c-dev` which can be installed on debian by running `sudo apt-get install libi2c-dev`.


## Building and running

This is forked from the parent which included a main and did not build as a shared library in a way that was easy to cross compile. This fork enables cmake to allow for it to more easily be able to cross compile and directly creates a shared library output installable.

To build
```
mkdir build
cd build
cmake ..
```

To install
```
cd build
make install DESTDIR=/usr
or
make install DESTDIR=/usr/local
```

Ensure that the device is correct for your adapter e.g. on Raspberry Pi Model A+ and Raspberry Pi 2 Model B the device is `/dev/i2c-1`.
