# DCS gRPC .Net Client

Part of the Dcs gRPC project.

## Installation

Install via nuget

## Example usage

```csharp
using Dcs;
using Grpc.Net.Client;

public void SendTextToAllPlayers(string host, int port, string text)
{
  using var channel = GrpcChannel.ForAddress($"http://{host}:{port}");
  var client = new Mission.MissionClient(channel);
  client.OutText( new OutTextRequest
  {
    Text = text
  });
}
```