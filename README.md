[![Community Forum](https://img.shields.io/badge/Community-Forum-41BDF5.svg?style=popout)](https://community.home-assistant.io/t/reef-pi-home-assistant-integration/312945)
[![hacs_badge](https://img.shields.io/badge/HACS-Custom-orange.svg)](https://github.com/custom-components/hacs)

[![GitHub release](https://img.shields.io/github/release/tdragon/reef-pi-hass-custom.svg)](https://github.com/reef-pi/reef-pi/releases)
![Pytest](https://github.com/tdragon/reef-pi-hass-custom/workflows/pytest/badge.svg?branch=master)
![Pytest](https://github.com/tdragon/reef-pi-hass-custom/workflows/hassfest/badge.svg?branch=master)
![GitHub All Releases](https://img.shields.io/github/downloads/tdragon/reef-pi-hass-custom/total)


# Home Assistane Reef Pi integration

This custom integration provides a way to sensors data and control equipment connected to [Reef-Pi (An open source reef tank controller based on Raspberry Pi)](http://reef-pi.github.io/).

## Installation

### Using [HACS](https://hacs.xyz/) (recommended)

This integration can be installed using HACS.
To do it add custom *integration* repository using url: `https://github.com/tdragon/reef-pi-hass-custom/`.
Then search for Reef Pi in *Integrations* section.

### Manual
To install this integration manually you have to download the content of this repository to `config/custom_components/reef-pi-hass-custom` directory:
```bash
mkdir -p custom_components/reef_pi
cd custom_components/reef_pi
curl -s https://api.github.com/repos/tdragon/reef-pi-hass-custom/releases/latest | grep "/reef_pi.zip"|cut -d : -f 2,3|tr -d \"| wget -i -
unzip reef_pi.zip
rm reef_pi.zip
```
After that restart Home Assistant.

## Configuration
Install integration from UI (Configuration --> Intergations --> + --> Search for `reef pi`)
Configuration options:
- Host (http://ip.address or https://ip.address)
- user name
- password
  
## Usage
Integration creates temperature sensor for each sensor connected to Reef PI: `sensor.{reef-pi name}_{temperature_sensor_name}`
Additionaly it create one sensor for CPU temperature: `sensor.{reef_pi_name}`

For each equipment configured in Reef Pi an outlet entity is created: `switch.{reef_pi name}_{equipment_name}`



