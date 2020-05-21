# Advanced Python Development Sunnboy Solar Sensors

This is an extension for apd.sensors that uses a command-line tool to extract
basic data from a Sunnyboy Solar Inverter

## Usage

Upon installing this sensor will be available to the sensor tools.

## Installation

You can install with `pip3 install apd.sunnyboy_solar` under Python 3.7 or higher.

We recommend using pipenv to manage your environment, in which case you would
install using `pipenv --three install apd.sunnyboy_solar`.

You must also have a tool installed that returns the values from your solar inverter.
I use https://github.com/simonswine/opensunny, which you must install, configure and
test before using this software.

This software only parses the human-readable output of that software, alternative
implementations will also work. The expected output format is:

    unusedstring yield_total=0000.000
    unusedstring power_dc_1=000
    unusedstring power_dc_2=000

Additional lines may be present, but will be ignored.

You must set some environment variables to communicate your configuration to this plugin.

They are:

    APD_SUNNYBOYSOLAR_PATH
    APD_SUNNYBOYSOLAR_BT_ADDRESS

The path is the full path to the executable that returns the data. The BlueTooth address
is the value to be passed to the executable's `-i` parameter.