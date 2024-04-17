# VoiceCommandManager Class Documentation

## Description
The `VoiceCommandManager` class manages voice commands within Unity applications. It allows registering and unregistering commands along with corresponding actions. It also interfaces with specific speech recognition implementations based on the platform.

## Public Methods

- `RegisterCommand(string command, Action action)`: Registers a voice command along with the corresponding action.
- `UnregisterCommand(string command)`: Unregisters a previously registered voice command.
- `InitializeSpeechRecognizer()`: Initializes the speech recognizer based on the platform.
  
## Private Methods

- `UpdateRecognizerCommands()`: Updates the recognizer's commands when commands are added or removed.
- `OnResult(string result)`: Invoked when a recognized voice command's result is received.
  
## Fields

- `Instance`: Static instance of the VoiceCommandManager.
- `speechRecognizer`: Interface for the speech recognizer implementation.
- `commands`: Dictionary storing registered voice commands and their corresponding actions.

## Unity Messages

- `Awake()`: Initializes the VoiceCommandManager and the speech recognizer on Awake.
## Platform Support

- **Windows**: Utilizes WindowsSpeechRecognizer for speech recognition on Windows 10 or later.
- **Android**: Utilizes AndroidSpeechRecognizer for speech recognition on Android devices.

This class does not currently support other platforms.

## Usage Example

```csharp
// Registering a voice command
VoiceCommandManager.Instance.RegisterCommand("Jump", () => Player.Jump());

// Unregistering a voice command
VoiceCommandManager.Instance.UnregisterCommand("Jump");