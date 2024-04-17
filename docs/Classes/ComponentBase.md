# ComponentBase Class Documentation

## Description
The `ComponentBase` class serves as a base class for components in the Arcon.Practice namespace. It provides functionality for handling pointer events, dragging, indicating interaction, and enabling/disabling interaction.

## Public Methods

- `SetDragConstraints(bool dragConstrain)`: Sets the drag constraints for the component.

- `EnableClick()`: Enables the click interaction for the component.

- `DisableClick()`: Disables the click interaction for the component.

- `EnableDrag()`: Enables dragging interaction for the component.

- `DisableDrag()`: Disables dragging interaction for the component.

- `EnableInteraction(bool enableOutline = true)`: Enables interaction for the component, optionally enabling outline indication.

- `DisableInteraction()`: Disables interaction for the component.

- `IndicateInteraction()`: Indicates interaction by showing an outline around the component.

- `IndicateWrongSelection()`: Indicates a wrong selection by showing a red outline around the component.

- `IndicateRightSelection()`: Indicates a correct selection by showing a green outline around the component.

- `HideIndication()`: Hides any indication (outline) around the component.

## Event Handlers

- `OnPointerClick(PointerEventData eventData)`: Handles the pointer click event.

- `OnPointerExit(PointerEventData eventData)`: Handles the pointer exit event.

- `OnDrag(PointerEventData eventData)`: Handles the drag event.

- `OnBeginDrag(PointerEventData eventData)`: Handles the beginning of a drag event.

- `OnEndDrag(PointerEventData eventData)`: Handles the end of a drag event.

## Additional Functionality

- `InstantiateClone()`: Instantiates a clone of the component for dragging purposes.

- `CheckRayPointer()`: Checks if the pointer ray intersects with another component.

## Knob Properties

- `EnableKnob(KnobProps.RotationAxis _rotationAxis)`: Enables knob functionality for the component.

- `DisableKnob()`: Disables knob functionality for the component.

- `setFinishValueKnob(float value)`: Sets the final value for the knob.

## KnobProps Class

The `KnobProps` class defines properties and functionality related to knob interaction.

## Events

- `OnChangeFloat`: UnityEvent for handling changes in float values.

