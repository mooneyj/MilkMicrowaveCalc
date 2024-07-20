# Milk Warmer Calculator

## Project Overview
The Milk Warmer Calculator is a Progressive Web App (PWA) designed to help parents quickly determine the optimal microwave heating time for baby milk. It calculates the time needed to warm milk to body temperature (37°C) based on the initial volume and temperature of the milk.

## Key Features
- Calculates warming time for milk volumes between 30-200ml
- Adjustable starting temperature
- Works offline once installed
- Compatible with both Android and iOS devices

## Underlying Physical Model

### Initial Linear Model
Our initial model was based on a simplified heat transfer equation:

t ≈ a * V + b * (37 - T_start)

Where:
- t = heating time (seconds)
- V = volume of milk (mL)
- T_start = starting temperature (°C)
- a ≈ 0.00919 (seconds per mL)
- b ≈ 1 (seconds per °C of temperature rise)

### Improved Non-Linear Model
After a couple of hours of experimentation in the kitchen, we had enough data to fit a non-linear model, which more accurately represents the heating process (specific heat capacity and conductivity of the bottle, room temp, bottle mass, surface area & temp...):

t = a * V^n + b * (T_target - T_start)^m + c

Where:
- t: Heating time (seconds)
- V: Volume of milk (mL)
- T_target: Target temperature (37°C)
- T_start: Starting temperature (°C)
- a, b, c, n, m: Constants determined by fitting to experimental data

### Experimental Process
We conducted a series of experiments to gather data for model fitting:
1. Various milk volumes (30ml to 200ml) were heated in a microwave.
2. Initial temperature and post-heating temperatures were recorded.
3. Multiple temperature measurements were taken after heating to account for heat transfer from the milk to the bottle and environment.
4. A 90-second standing time was chosen as representative of real-world usage.

### Model Fitting
The experimental data was used to fit the non-linear model using a regression analysis. The resulting parameters are:

- a ≈ 3.939 × 10^-5
- b ≈ -641.627
- c ≈ 661.189
- n ≈ 2.739
- m ≈ 0.0035

This model provides a more accurate representation of the heating process, accounting for:
- Non-linear relationships between volume and heating time
- The effect of starting temperature
- Heat transfer between milk, bottle, and environment during the standing time

## Usage:

1. Enter the volume of milk in milliliters
2. Enter the starting temperature (defaults to 3°C for refrigerated milk)
3. Click 'Calculate' to get the recommended microwave time

## Setting up the PWA

This app is designed as a Progressive Web App (PWA), which means you can install it on your home screen for quick access, just like a native app.

### For Android:

1. Open the app's URL in Google Chrome.
2. Tap the menu icon (three dots) in the top right corner.
3. Select "Add to Home screen" from the dropdown menu.
4. Choose a name for the app shortcut (or keep the default) and tap "Add".
5. The app icon will now appear on your home screen.

### For iOS:

1. Open the app's URL in Safari.
2. Tap the Share button (the square with an arrow pointing upward) at the bottom of the screen.
3. Scroll down and tap "Add to Home Screen".
4. Choose a name for the app shortcut (or keep the default) and tap "Add".
5. The app icon will now appear on your home screen.

Note: On iOS, you must use Safari for the "Add to Home Screen" option to appear.

## Offline Usage

Once installed as a PWA, the Milk Warmer Calculator can be used offline. Make sure to open the app at least once while online to allow it to cache necessary files.


## Note:

Always test the temperature of the milk before feeding. Adjust heating times based on your specific microwave's performance.

## Technical Implementation
The app is implemented as a PWA with the following components:
- index.html: Main app interface
- manifest.json: PWA configuration
- service-worker.js: Enables offline functionality
- Icon files: For app installation and branding

The calculation logic is implemented in JavaScript, using the fitted non-linear model to provide accurate heating time estimates.

## Potential Future Improvements
- Create a hybrid physical/blind model: Additonal input parameters of bottle starting temperature, choice of a bottle model and room temperature. Would account for a significant portion of the observed model error.
- Incorporation of microwave power as a user input for transferability.
- Further experimentation to refine model.
- Addition of a safety feature to warn against overheating & remind always to test on back of hand.
