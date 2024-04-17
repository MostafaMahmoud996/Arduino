# ReadingAction Class Documentation

## Table of Contents

- [Overview](#overview)
- [ReadingDevice Nested Class](#readingdevice-nested-class)
- [Fields and Properties](#fields-and-properties)
- [Public Methods](#public-methods)
- [Implementation Details](#implementation-details)
- [Clone Method](#clone-method)

## Overview

`ReadingAction` is a class that implements the `IAction` interface, designed to manage reading actions within the Arcon.Practice namespace. It facilitates the interaction with devices and reading components, handling user inputs and validations in the context of an experiment.

## ReadingDevice Nested Class

### Overview

Nested within the `ReadingAction` class, `ReadingDevice` is used to define devices capable of reading actions, including validation for the presence of required methods and properties.

### Fields

- `device`: An instance of `Device` that represents the physical or virtual device.
- `ReadingID`: A unique identifier for the reading action on the device.

### Validation Methods

- `HasReadingMethod()`: Checks if the `device` has a method named `SetReading`.
- `checkReadingID()`: Validates that the `ReadingID` is not empty or null.

## Fields and Properties

- `readingComponents`: A dictionary mapping string identifiers to `ReadingComponent` objects.
- `device`: A list of `ReadingDevice` instances that are part of the reading action.
- `userInputs`: A dictionary to store user inputs with string identifiers as keys and float values.

## Public Methods

### `ListentoAction()`

An `IEnumerator` method that orchestrates the reading action process, setting text in reading components, invoking device methods, enabling user input columns, and validating user inputs.

### `SendAction<T>(T sender, string parameter = null)`

Processes actions sent to the `ReadingAction` object, particularly handling submission of user inputs.

### `Clone()`

Creates a deep copy of the `ReadingAction` instance, ensuring cloned instances can be used independently of the original.

## Implementation Details

- Validates user inputs against predefined criteria, ensuring inputs fall within acceptable ranges.
- Dynamically calls device-specific functions to set readings based on identifiers.
- Manages error indications based on input validation results.

## Clone Method

Provides functionality to create a deep copy of the `ReadingAction` instance. The clone method ensures that the new instance is independent, allowing for actions to be reused with different configurations without affecting the original instance's state.

This documentation outlines the functionalities and usage of the `ReadingAction` class within Unity projects, providing a comprehensive guide for developers to implement and extend reading actions in their simulations or educational applications.
