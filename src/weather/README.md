# Weather MCP Server

A custom MCP (Machine Configuration Protocol) server for retrieving weather information directly in Cursor.app.

## Features

- Real-time weather data using OpenWeather API
- Seamless integration with Cursor.app
- Easy configuration and setup

## Prerequisites

- MacOS
- Cursor.app installed
- Python 3.8 or higher
- OpenWeather API key ([Get one here](https://openweathermap.org/api))

## Installation

1. Create a new MCP server:
```bash
uvx create-mcp-server
```

2. During setup:
   - Follow the prompts
   - Select 'y' when asked about Cursor.app integration

3. Navigate to your server directory and install dependencies:
```bash
cd your_server_directory
uv sync --dev --all-extras
uv pip install python-dotenv
```

4. Configure your server:
   - Modify `server.py` according to your needs
   - Create and update the `.env` file with your settings

5. Test your installation:
```bash
uv run server_name
```

## Cursor.app Configuration

Add the following configuration to your Cursor settings:

```json
{
  "mcpServers": {
    "weather": {
      "command": "uv",
      "args": [
        "--directory",
        "/path/to/server",
        "run",
        "weather"
      ],
      "env": {
        "OPENWEATHER_API_KEY": "your_api_key"
      }
    }
  }
}
```

> ⚠️ Remember to replace `/path/to/server` with your actual server path and `your_api_key` with your OpenWeather API key.

## Usage

Once configured, you'll have instant access to weather information directly in Cursor.app. Never wonder about the weather again!

## Troubleshooting

If you encounter any issues:
1. Verify your API key is correct
2. Check your server path in the Cursor configuration
3. Ensure all dependencies are properly installed
4. Check the server logs for any error messages
