# Local AI Setup

This project runs a local AI model using **Ollama** and a PowerShell startup script.

## Requirements

* Windows
* Node.js **LTS**
* Ollama
* PowerShell

## 1. Install Node.js LTS

Download and install the latest **LTS version of Node.js** from the official website:

[Node.js Official Website](https://nodejs.org/?utm_source=chatgpt.com)

After installation, verify that Node.js and npm are available:

```powershell
node --version
npm --version
```

## 2. Install Ollama

Download and install Ollama for Windows:

[Ollama Official Website](https://ollama.com/?utm_source=chatgpt.com)

After installation, verify that Ollama is installed:

```powershell
ollama --version
```

## 3. Download the AI Model

Open **PowerShell** in the project directory and run:

```powershell
ollama pull gemma4:e2b
```

This downloads the `gemma4:e2b` model to your local machine.

You can check that the model was downloaded with:

```powershell
ollama list
```

You should see:

```text
gemma4:e2b
```

## 4. Start the Application

Make sure you are in the project directory containing `start-local.ps1`.

Run:

```powershell
powershell -ExecutionPolicy Bypass -File .\start-local.ps1
```

The startup script will launch the local application and connect it to the Ollama model.

## Quick Start

If Node.js and Ollama are already installed, run the following commands from the project directory:

```powershell
ollama pull gemma4:e2b
powershell -ExecutionPolicy Bypass -File .\start-local.ps1
```

## Troubleshooting

### `ollama` is not recognized

If PowerShell shows:

```text
'ollama' is not recognized as the name of a cmdlet...
```

Make sure Ollama is installed and restart PowerShell.

You can verify the installation with:

```powershell
ollama --version
```

### Model not found

If the application cannot find the model, run:

```powershell
ollama pull gemma4:e2b
```

Then verify:

```powershell
ollama list
```

### PowerShell execution policy error

If PowerShell blocks the startup script, use:

```powershell
powershell -ExecutionPolicy Bypass -File .\start-local.ps1
```

This bypasses the execution-policy restriction for this command only.

## Project Structure

```text
project/
├── start-local.ps1
├── package.json
├── README.md
└── ...
```

## Notes

The AI model runs **locally through Ollama**. No external API key is required for the local model.
