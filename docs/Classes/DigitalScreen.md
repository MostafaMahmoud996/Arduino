# DigitalScreen Class Documentation

## Table of Contents
- [Overview](#overview)
- [Public Properties](#public-properties)
- [Public Methods](#public-methods)
- [Private Methods](#private-methods)
- [Attributes](#attributes)

## Overview
The `DigitalScreen` class is a component designed for use in Unity projects. It provides functionality for displaying a digital-style screen with customizable number formatting, colors, and flickering effects.

## Public Properties
- `Value`: Property to get or set the current value displayed on the digital screen.

## Public Methods

- `Awake()`: Initializes the digital screen component.

- `UpdateDigit()`: Updates the digit displayed on the screen by moving from the current digit to the next one towards the right. If it arrives at the end digit, it wraps around to the first digit.

- `StartDigitFlicker(int digitIndexToFlicker, float flickerDuration)`: Initiates a flickering effect on a specific digit identified by `digitIndexToFlicker`. The flicker lasts for the specified `flickerDuration`.

- `FlickerDigitCoroutine(int digitIndexToFlicker, float flickerDuration)`: Coroutine method for creating a flickering effect on a specific digit. This method is called internally by `StartDigitFlicker`.

- `FormatText(float number)`: Formats the provided `number` into a string representation suitable for display on the digital screen.

- `FormatText(string textBeforeFormat)`: Formats the provided `textBeforeFormat` string into a displayable format according to the predefined digit sprites.

- `IncreaseDigitValue()`: Increases the value displayed on the screen by the increment value specified in the `incrementValue` attribute.

- `DecreaseDigitValue()`: Decreases the value displayed on the screen by the decrement value specified in the `incrementValue` attribute.

- `UpdateValue(float number)`: Updates the value displayed on the screen to the specified `number`.

- `StopFlickerCoroutine()`: Stops the flickering coroutine.

- `EndEditMode()`: Ends the edit mode and resets the digital screen to its original state, stopping any ongoing flickering effects and resetting the displayed value.


## Private Methods
- `reset()`: Coroutine method to reset the digital screen.

## Attributes
- `numberFormat`: String representing the format of the displayed number.
- `color`: Color of the digits displayed on the screen.
- `text`: TextMeshProUGUI component used for displaying text.
- `incrementValue`: Increment value for increasing or decreasing the displayed number.
- `number`: Current value displayed on the screen.
- `maxNumber`: Maximum value allowed on the screen.
- `miniNumber`: Minimum value allowed on the screen.
- `currentIndex`: Index of the current digit being manipulated.
- `flickerDuration`: Duration of the flickering effect.
- `digits`: Dictionary mapping digit strings to sprite names for display.
- `flickerCoroutine`: Coroutine for managing the flickering effect.
- `hasDot`: Boolean indicating whether the number format includes a decimal point.
