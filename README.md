# Milk Warmer Calculator

A simple yet precise Progressive Web App (PWA) designed to calculate microwave heating times for baby milk. This tool helps parents quickly determine the optimal time to warm milk to body temperature (37°C) based on volume and starting temperature.

## Features:

- Calculates heating time for milk volumes between 30-1000ml
- Adjustable starting temperature
- Based on physics principles of heat transfer
- Works offline as a PWA
- Compatible with both Android and iOS devices

## How it works:

This calculator uses a formula derived from the physics of heating, taking into account:
- Microwave efficiency (55% of 800W)
- Specific heat capacity of milk (3.93 kJ/(kg·°C))
- Density of milk (1.03 kg/L)
  This is good initial best guesss from first principles, but the two constants can be adjusted for a particular microwave, after performing a small series of heating experiments (will test and see if this is needed later).

The app provides a quick, easy-to-use interface for parents to ensure their baby's milk is heated to the perfect temperature, every time.

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
