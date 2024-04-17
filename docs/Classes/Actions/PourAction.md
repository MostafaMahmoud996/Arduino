# PourAction Class Documentation

## Table of Contents

- [Overview](#overview)
- [Public Fields and Properties](#public-fields-and-properties)
- [Public Methods](#public-methods)
- [Implementation Details](#implementation-details)
- [Clone Method](#clone-method)

## Overview

The `PourAction` class is designed to manage pour actions within Unity projects, particularly in the context of interactive simulations or games. It implements the `IAction` interface and coordinates the interaction between liquid containers (`LiquidContainer` objects), enabling the simulation of pouring actions, including handling multiple liquid layers, adjusting camera angles, and executing post-pour behaviors.

## Public Fields and Properties

### Drag Configuration

- `_dragObject`: The `LiquidContainer` object that will be dragged.
- `_dropObject`: The `LiquidContainer` object that will receive the liquid.
- `_WrongObjects`: A list of `ComponentBase` objects that should not be interacted with during the pour action.

### Pour Configuration

- `requiredQuantity`: The quantity of liquid to be poured.
- `isMultipleLiquid`: A flag indicating if the pouring action involves multiple liquid types.
- `sourceLayerIndex`: The layer index in the source container from which the liquid is poured (applicable when `isMultipleLiquid` is true).
- `targetLayerIndex`: The layer index in the target container to which the liquid is poured (applicable when `isMultipleLiquid` is true).
- `virtualCamera`: A `CinemachineVirtualCamera` object for controlling camera view during the pour action.
- `changeAngle`: A flag indicating if the angle of pouring should be changed.
- `pourAngle`: The angle at which the liquid is to be poured (applicable when `changeAngle` is true).

### Post-Behavior Configuration

- `PostBehaviors`: A list of `IStepBehavior` objects that define behaviors to execute after the pour action is completed.

## Public Methods

### `ListentoAction()`

An `IEnumerator` method that orchestrates the pour action, enabling and disabling interactions and drag functionalities, handling wrong object interactions, and executing post-behaviors.

### `SendAction<T>(T sender, string parameter = null)`

Method for receiving action commands, with the ability to differentiate between drag, drop, and pour actions based on the provided parameter.

### `ValidateTarget(ComponentBase component)`

Validates the target of the pour action, indicating whether the selection is correct or wrong.

### `Clone()`

Creates a deep copy of the `PourAction` instance, ensuring that the cloned instance is independent of the original.

## Implementation Details

The `PourAction` class integrates closely with the `LiquidContainer` class to simulate pouring actions. It utilizes Unity's coroutine system to sequence the actions and behaviors. The class leverages Sirenix.OdinInspector for enhanced inspector functionality, making it easier to configure actions and behaviors directly within the Unity Editor.

## Clone Method

The clone method is particularly important for creating independent copies of actions, allowing for the reuse of pour action configurations with different objects or parameters without affecting the original action's state.

This documentation outlines the functionalities and usage of the `PourAction` class within Unity projects, providing a guide for developers to integrate and extend interactive pour actions in their simulations or games.
