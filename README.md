# JSON-Flattener

[![gh-page](https://github.com/CLown1331/JSON-Flattener/actions/workflows/gh-pages.yml/badge.svg)](https://github.com/CLown1331/JSON-Flattener/actions/workflows/gh-pages.yml)

Try it out: https://clown1331.github.io/JSON-Flattener/

Will flatten with ASP.NET json seperator `:`

Example:

```
{
  "Logging": {
    "LogLevel": {
      "Default": "Debug",
      "System": "Information",
      "Microsoft": "Information"
    }
  },
  "Serilog": {
    "Using": [  "Serilog.Sinks.Seq", "Serilog.Sinks.Console" ],
    "WriteTo": [
      { "Name": "Console" },
      {
        "Name": "Seq",
        "Args": { "serverUrl": "http://localhost:5341/" }
      }
    ]
  }
}
```

```
{
    "Logging:LogLevel:Default": "Debug",
    "Logging:LogLevel:System": "Information",
    "Logging:LogLevel:Microsoft": "Information",
    "Serilog:Using:0": "Serilog.Sinks.Seq",
    "Serilog:Using:1": "Serilog.Sinks.Console",
    "Serilog:WriteTo:0:Name": "Console",
    "Serilog:WriteTo:1:Name": "Seq",
    "Serilog:WriteTo:1:Args:serverUrl": "http://localhost:5341/"
}
```
