# TDCode: Integrated Code Editor for TouchDesigner

## Overview
TDCode is a high-performance, integrated code editor component for TouchDesigner. It provides a seamless, IDE-like experience within your TouchDesigner projects, offering syntax highlighting, project-specific autocompletions, and rapid access to any DAT or OP in your network.

## Key Features
- **One-Click Integration:** Drag and drop TDCode into your project for instant setup.
- **TouchDesigner-Specific Syntax Highlighting:** Optimized for Python, GLSL, and other TD-relevant languages.
- **Project-Wide Autocompletion:** Intelligent suggestions based on your entire TD network.
- **Rapid DAT/OP Access:** Quickly navigate and edit any DAT or OP in your project.
- **Real-Time Sync:** Changes reflect immediately in TouchDesigner for instant feedback.
- **Advanced Editor Features:** Powered by Monaco Editor, configurable to your liking at 'editor/editor_config_js'.
- **Custom UI and Shortcuts:** Tailored interface and keyboard shortcuts for TD workflows.
- **AI-Powered Code Completion:** Integrated Monacopilot for intelligent code suggestions.
- **Terminal Chat Command:** Interactive chat via `chat` command with model selection and chat history options.

## Installation
1. Drag and drop TDCode into your project.
2. TDCode will automatically initialize and integrate with your project.
3. Press the TDCode button in the main panel, or press 'Ctrl+T' to open TDCode's editor panel.
4. No additional setup or configuration is required.

## Navigating DATs and OPs
- Use 'Alt+Shift+S' to open the DAT selection dropdown.
- Use 'Alt+Shift+O' to open the OP selection dropdown.
- Use 'Alt+Shift+N' to open the Navigation Tree.
- Type in the dropdown search field to quickly filter and find your target DAT/OP.

## Editing Code
- Select a DAT or OP from the dropdowns to edit.
- Modify the code in the main editor window.
- Changes are automatically synced with TouchDesigner in real-time.

## Leveraging Autocompletions
- As you type, TDCode will offer context-aware suggestions.
- Autocompletions include:
  - TouchDesigner built-in functions and modules
  - Custom operators and parameters from your project
  - Python standard library
  - AI-powered suggestions from Monacopilot
  - Use 'Ctrl+Shift+Space' to trigger AI completions in onDemand mode, or type to trigger completions in onIdle & onTyping modes.

## Utilizing Syntax Highlighting
TDCode automatically detects and applies appropriate syntax highlighting. Supported languages include:
- Python (optimized for TouchDesigner)
- GLSL
- JSON
- HTML/CSS
- JavaScript / TypeScript

## Keyboard Shortcuts
- 'Ctrl+F': Find
- 'Ctrl+H': Replace
- 'Alt+Up/Down': Move line up/down
- 'Ctrl+/': Toggle line comment

## Advanced Features

### Monarch Language Models
TDCode implements a Monarch language & syntax highlighter to provide TD-specific language features:
- Hover information for TD operators and parameters.
- Go-to-definition for custom components and modules.
- Real-time error checking and linting.

For more information on Monarch, visit: https://microsoft.github.io/monaco-editor/monarch.html

### AI-Powered Code Completion
TDCode now integrates Monacopilot, providing intelligent code suggestions:
- Context-aware completions based on your current code and project structure.
- Support for TouchDesigner-specific code patterns and best practices.
- Real-time suggestions as you type.

For more information on Monacopilot, visit https://github.com/arshad-yaseen/monacopilot

## Terminal Commands

### `chat` Command
The `chat` command allows users to interact with a chat model by sending messages to it. This command also provides options to utilize chat history and select specific models for the conversation. The `chat` command works with the [https://openrouter.ai](https://openrouter.ai) API.

#### Usage
```bash
chat [-h|--history] <model> : <message>
```

#### Parameters
- `-h`, `--history`:  
  Optional flag that, when provided, uses the chat history during the conversation. This helps maintain the context of previous interactions with the model.
  
- `-p [paths]`:  
  Allows you to send specific DAT or OP context paths for more informed responses from the chat model.
  
- `<model>`:  
  Specifies the model to use for the chat interaction. If not provided, the default model is set to `deepseek/deepseek-chat`.

- `<message>`:  
  The message to be sent to the chat model. This is the main text input that the model will process and respond to.

#### Examples
1. **Basic Chat Interaction with Default Model**:
```bash
chat deepseek/deepseek-chat : Hello, how are you?
```

2. **Chat Interaction Using Chat History**:
```bash
chat -h deepseek/deepseek-chat : Continue our discussion on quantum computing.
```

3. **Chat Interaction with Specified Model and Context**:
```bash
chat -h -p [path/to/context.dat, path/to/context.op] deepseek/deepseek-chat : Analyze this data.
```

4. **Reuse Previous Context**:
```bash
chat * deepseek/deepseek-chat : How does this data compare to our last chat?
```

## Extending TDCode
Developers can extend TDCode's capabilities:
- Remove 'TDCode/*' from the DAT Settings 'excludepath' parameter to access and modify core functionality.
