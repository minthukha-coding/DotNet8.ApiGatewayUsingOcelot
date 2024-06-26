
# DotNet8.ApiGatewayUsingOcelot
 
This repository demonstrates how to implement an API Gateway using Ocelot in a .NET 8 application.

## Features

- **API Gateway**: Centralized entry point for multiple backend services.
- **Routing**: Simplified routing configuration using Ocelot.
- **Configuration**: Manage routes and other settings through `ocelot.json` and `ocelot.routes.json`.

## Getting Started

### Prerequisites

- .NET 8 SDK

### Installation

1. Clone the repository:
    ```bash
    git clone https://github.com/minthukha-coding/DotNet8.ApiGatewayUsingOcelot.git
    cd DotNet8.ApiGatewayUsingOcelot
    ```

2. Restore dependencies:
    ```bash
    dotnet restore
    ```

3. Build the project:
    ```bash
    dotnet build
    ```

### Running the Application

1. Run the application:
    ```bash
    dotnet run
    ```

2. The API Gateway will be available at `http://localhost:5000`.

## Configuration

- **`ocelot.json`**: Main configuration file for Ocelot.
- **`ocelot.routes.json`**: Routes configuration file.

### Example Configuration

```json
{
  "Routes": [
    {
      "DownstreamPathTemplate": "/api/{everything}",
      "DownstreamScheme": "http",
      "DownstreamHostAndPorts": [
        {
          "Host": "localhost",
          "Port": 5001
        }
      ],
      "UpstreamPathTemplate": "/gateway/{everything}",
      "UpstreamHttpMethod": [ "GET", "POST", "PUT", "DELETE" ]
    }
  ],
  "GlobalConfiguration": {
    "BaseUrl": "http://localhost:5000"
  }
}
