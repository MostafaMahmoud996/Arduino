# LiquidContainer Class Documentation

## Table of Contents

- [Overview](#overview)
- [Public Properties](#public-properties)
- [Public Methods](#public-methods)
- [Private Methods](#private-methods)
- [Attributes](#attributes)
- [Unity Events](#unity-events)
- [Drip Functionality](#drip-functionality)
- [Serializable Classes](#serializable-classes)

## Overview

The `LiquidContainer` class is a component designed for managing liquid containers in Unity projects. It leverages various libraries such as DG.Tweening for animations, Doozy for UI management, LiquidVolumeFX for visual effects, and Sirenix.OdinInspector for enhanced inspector functionality. This class provides functionalities for simulating pouring and dripping behaviors between containers, adjusting liquid levels, controlling visual effects, and dynamically modifying liquid properties such as color, opacity, and smoke.

## Public Properties

- `_liquidVolume`: A reference to the `LiquidVolume` component representing the container's liquid volume.
- `_FullCapacityVolume`: Specifies the full capacity volume of the container.
- `_FullMeshLevel`: Indicates the level at which the mesh represents a full container.
- `Volume`: Current volume of liquid in the container, adjustable via UI elements or script.
- `isMultipleLiquid`: Indicates whether the container supports multiple types of liquids, enabling layered liquid simulation.

## Public Methods

### Liquid Adjustment Methods

- `ChangeAdjustmentLayerSpeed(float _targetSpeed, int _layer)`: Adjusts the speed at which liquid layers reach their target state.
- `ChangeSmokeVisibility(bool _targetSmokeVisibility)`: Enables or disables smoke effects.
- `ChangeBubblesVisibility(int _targetBubblesVisibility, int _layer)`: Adjusts the visibility of bubbles within a specific layer.
- `ChangeBubblesOpacity(float targetBubblesOpacity, float duration, int layerIndex)`: Animates the opacity of bubbles over a specified duration.
- `ChangeLiquidColor1(Color targetColor, float duration)`: Animates the change of the primary liquid color over time.
- `ChangeLiquidSmokeColor(Color targetSmokeColor, float duration)`: Changes the smoke color of the liquid over a specified duration.
- `ChangeLiquidColor(Color targetColor, float duration, int layerIndex)`: Changes the color of a specific liquid layer.
- `ChangeAmount(float targetAmount, float duration, int layerIndex)`: Modifies the amount of liquid in a specified layer.

### Liquid Simulation Methods

- `TakeLiquid(float _volume, float _time)`: Removes a specified volume of liquid from the container.
- `AddLiquid(float _volume, float _time)`: Adds a specified volume of liquid to the container.
- `ChangeLiquidVolume(float volumeChange, float duration, float delay = 0)`: Dynamically changes the volume of liquid in the container.
- `EnablePour(LiquidContainer _emptyCup, LiquidContainer _fullCup, float _angle, bool changeAngle)`: Initiates the pouring process between two containers.
- `DisablePour()`: Stops the pouring process.
- `EnableDrip(LiquidContainer _emptyCup, LiquidContainer _fullCup, float requiredQuantity)`: Enables the dripping functionality between two containers.
- `DisableDrip()`: Disables the dripping functionality.

## Private Methods

Contains internal methods for handling pouring and dripping mechanics, updating UI elements, and managing liquid levels.

## Attributes

Decorated fields and properties with attributes such as `[FoldoutGroup]`, `[OnValueChanged]`, and `[PropertyRange]` for enhanced organization and interaction within the Unity Inspector.

## Unity Events

- `OnBeginDrag(PointerEventData eventData)`: Initiates pouring or dragging functionality based on input.
- `OnEndDrag(PointerEventData eventData)`: Ends pouring or dragging interactions.
- `OnPointerClick(PointerEventData eventData)`: Handles click events for initiating or reverting drip functionality.

## Drip Functionality

Details methods and logic for simulating drip effects between containers, including enabling, disabling, and reversing drip actions.

## Serializable Classes

- `AngleRange`: A utility class for defining the range of angles for pouring actions, with properties to manage minimum and maximum angles.

This documentation outlines the structure and capabilities of the `LiquidContainer` class, offering a comprehensive guide for integrating and extending its functionalities within Unity projects.
