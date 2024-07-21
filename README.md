# Milk Warmer Calculator

## Project Overview
The Milk Warmer Calculator is a Progressive Web App (PWA) designed to help parents quickly determine the optimal microwave heating time for baby milk. It calculates the time needed to warm milk to body temperature (37°C) based on the initial volume and temperature of the milk.

## Key Features
- Calculates warming time for milk volumes between 30-1000ml
- Adjustable starting temperature
- Works offline once installed
- Compatible with both Android and iOS devices

## Underlying Physical Model

The calculator uses a linear model based on experimental data to estimate the heating time. The model takes into account both the volume of milk and the temperature difference:

t = a * V + b * (T_target - T_start) + c

Where:
- t = heating time (seconds)
- V = volume of milk (mL)
- T_target = target temperature (37°C)
- T_start = starting temperature (°C)
- a = 0.246 (coefficient for volume)
- b = -0.310 (coefficient for temperature difference)
- c = 9.777 (constant term)

This model provides a good approximation of heating times across a wide range of milk volumes and starting temperatures.

## Experimental Process
The model parameters were determined through a series of experiments:
1. Various milk volumes (30ml to 1000ml) were heated in a microwave.
2. Initial temperature and post-heating temperatures were recorded.
3. Multiple temperature measurements were taken after heating to account for heat transfer from the milk to the bottle and environment.
4. A standard standing time was chosen as representative of real-world usage.

## Usage Notes
- Users are always advised to check the milk's temperature before feeding, as microwave heating can be uneven.
- The app provides a quick estimate, but factors like microwave power and bottle material may affect actual heating time.
- The default quantity is set to 45ml for convenience, but can be easily adjusted.

## Technical Implementation
The app is implemented as a PWA with the following components:
- index.html: Main app interface
- manifest.json: PWA configuration
- service-worker.js: Enables offline functionality
- Icon files: For app installation and branding

The calculation logic is implemented in JavaScript, using the linear model to provide heating time estimates.

## Future Improvements
- Refinement of the model based on additional experimental data
- Incorporation of microwave power as a user input for more precise calculations
- Addition of a safety feature to warn against overheating
