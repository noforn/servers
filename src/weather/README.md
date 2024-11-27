Usage on Claude Desktop (MacOS):  

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
