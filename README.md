# MassTransit RabbitMQ Getting Started

## Project Overview
A .NET 8 messaging application demonstrating MassTransit with RabbitMQ integration.

## Prerequisites
- .NET 8 SDK
- Docker
- RabbitMQ

## Key Components
- Message Publishing
- Message Consuming
- RabbitMQ Transport

## Quick Start

### Installation
```bash
# Add required packages
dotnet add package MassTransit.AspNetCore
dotnet add package MassTransit.RabbitMQ
```

### Configuration
Update `Program.cs`:
```csharp
services.AddMassTransit(x =>
{
    x.AddConsumer<MessageConsumer>();
    x.UsingRabbitMq((context, cfg) =>
    {
        cfg.ConfigureEndpoints(context);
    });
});
```

### Running the Application
```bash
# Start containers
docker-compose up --build
```

## Development Patterns
- Create message contracts as POCO classes
- Implement consumers for message processing
- Use `IBus` for message publishing

## Next Steps
- Implement complex messaging scenarios
- Add robust error handling
- Configure advanced message routing
- Explore persistent message storage

## Useful Links
- [MassTransit Documentation](https://masstransit-project.com/getting-started/)
