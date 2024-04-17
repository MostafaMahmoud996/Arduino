# VoiceCommandUI Class Documentation

## Description
The `VoiceCommandUI` class allows for easy integration of voice commands with various UI elements in Unity. It supports different types of UI elements such as buttons, toggles, event triggers, and Unity events, enabling developers to associate voice commands with corresponding actions.

## Public Fields

- `type`: Specifies the type of UI element and its associated functionality.
- `command`: The voice command associated with the UI element.
- `commandON`: The voice command associated with toggling the UI element ON (specifically for toggles).
- `commandOFF`: The voice command associated with toggling the UI element OFF (specifically for toggles).
- `onCommandTrigger`: UnityEvent triggered by the voice command (specifically for UnityEvent type).

## Enumerations

- `VoiceCommandUIType`: Enumerates the types of UI elements supported by the VoiceCommandUI class.

## Serialized Classes

- `EventTriggerComands`: Serialized class representing a mapping between EventTriggerType and the associated voice command.

## Unity Messages

- `Awake()`: Initializes the VoiceCommandUI and checks for the presence of necessary components.
- `OnEnable()`: Coroutine to register voice commands when the object is enabled.
- `OnDisable()`: Unregisters voice commands when the object is disabled.

## Private Methods

- `OnTypeChange()`: Callback method invoked when the UI type is changed, checks for the presence of required components.
- `RegisterCommands()`: Coroutine to register voice commands based on the UI type.
- `UnregisterCommands()`: Unregisters previously registered voice commands.
- `RegisterButtonCommand()`: Registers voice command for button click events.
- `RegisterToggleCommands()`: Registers voice commands for toggle events.
- `RegisterEventTriggerCommands()`: Registers voice commands for event trigger events.

## Platform Support

- **Windows**: Utilizes the VoiceCommandManager class for voice command registration and execution.
- **Android**: Utilizes the VoiceCommandManager class for voice command registration and execution.

This class is platform-independent and supports voice command integration in Unity applications across different platforms.

## Usage Instructions

### Inspector Setup

1. **Attach Script**: Attach the `VoiceCommandUI` script to a GameObject in your Unity scene.

2. **Inspector Configuration**:

   - **Type**: Choose the type of UI element (Button, Toggle, EventTrigger, UnityEvent).
   
   - **Commands**: Depending on the type, provide the necessary voice command(s).
   
   - **Additional Configuration**: Some types might require additional configuration, such as specifying commands for toggling on and off.

3. **Speech Recognition Setup**:

   - Ensure that the `VoiceCommandUI` component has access to the `VoiceCommandManager` instance. This typically means having an instance of `VoiceCommandManager` in your scene.
   
   - When the scene starts, the `VoiceCommandUI` component automatically registers the specified voice commands with the `VoiceCommandManager`.
