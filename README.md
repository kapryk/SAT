# Smart Autotune Thermostat (SAT)
The Smart Autotune Thermostat (SAT) is a custom component for Home Assistant that works with an [OpenTherm Gateway (OTGW)](https://otgw.tclcode.com/) in order to provide advanced temperature control functionality based on the Proportional-Integral-Derivative (PID) algorithm. Unlike other thermostat components, SAT supports automatic gain tuning and heating curve coefficient, which means it can determine the optimal setpoint for your boiler without any manual intervention.

## Features
- Multi-room temperature control with support for temperature synchronization for main climates
- Adjustable heating curve coefficients to fine-tune your heating system
- Target temperature step for adjusting the temperature in smaller increments
- Presets for different modes such as Away, Sleep, Home, Comfort
- Automatic gains for PID control
- Overshoot protection to prevent the boiler from overshooting the setpoint
- Climate valve offset to adjust the temperature reading for your climate valve
- Sample time for PID control to fine-tune your system's response time

## Installation
### Manual
1. Download the latest release of the SAT custom component from the GitHub repository.
2. Copy the sat directory to the custom_components directory in your Home Assistant configuration directory. If the custom_components directory doesn't exist, create it.
3. Restart Home Assistant to load the SAT custom component.
4. After installing the SAT custom component, you can configure it via the Home Assistant Config Flow interface.

### HACS
1. Install <a href="https://hacs.xyz/">HACS</a> if you haven't already.
2. Open the HACS web interface in Home Assistant and navigate to the Integrations section.
3. Click the three dots in the top-right corner and select "Custom repositories".
4. Enter the URL of the SAT custom component GitHub repository (https://github.com/Alexwijn/SAT) and select "Integration" as the category. Click "Add".
5. Once the SAT custom component appears in the list of available integrations, click "Install" to install it.
6. Restart Home Assistant to load the SAT custom component.
7. After installing the SAT custom component, you can configure it via the Home Assistant Config Flow interface.

## Configuration
SAT is configured using a config flow. After installation, go to the Integrations page in Home Assistant, click on the Add Integration button, and search for SAT. Follow the prompts to configure the integration.

## Multi-room setup
In multi-room mode, SAT monitors the climates in other rooms to determine the error and calculates how much heat is needed. It selects the highest error value as the error value for the current room, instead of using the average temperature across all rooms. This ensures that the temperature in each room is maintained at its desired level.

Note that SAT assumes that the climate control systems in the additional rooms are smart and won't exceed their target temperatures, as this can cause inefficiencies in the overall system. Once every climate control system in all rooms is around the target temperature, SAT can operate at its most efficient level.

## Heating Curve Coefficient
The heating curve coefficient is a configurable parameter in SAT that allows you to adjust the relationship between the outdoor temperature and the heating system output. This is useful for optimizing the heating system's performance in different weather conditions, as it allows you to adjust how much heat the system delivers as the outdoor temperature changes. By tweaking this parameter, you can achieve a more efficient and comfortable heating system.

## Automatic gains
SAT supports automatic PID gain tuning. When this feature is enabled, SAT will continuously adjust the PID gains to optimize the temperature control performance based on the current conditions instead of manually filling in the PID-values.

## Overshoot protection
With overshoot protection enabled, SAT will automatically calculate the maximum allowed modulation value for the boiler based on the setpoint and the calculation overshoot protection value.

## Support
If you want to support this project, you can [**buy me a coffee here**](https://www.buymeacoffee.com/alexwijn).

<a href="https://www.buymeacoffee.com/alexwijn"><img src="https://img.buymeacoffee.com/button-api/?text=Buy me a coffee&emoji=&slug=alexwijn&button_colour=0ac982&font_colour=000000&font_family=Cookie&outline_colour=000000&coffee_colour=ffffff"></a>
