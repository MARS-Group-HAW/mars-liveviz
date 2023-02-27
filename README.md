# MARS Simple Visualization

A simple visualization to consume the real-time simulation output of a MARS model with it's WebSocket output.

You can use it to visualize Grid-Based models in real-time.

## Installation

- Open your terminal and navigate into this directory. 
- Install [Python](https://www.python.org/downloads/).
- Install dependencies with `$ pip install -r requirements.txt`

## Start

Start the mini visualization by calling `$ python main.py`. The visualization now waits for a MARS simulation to run.

## Configure your model

In the MARS model you want to visualize, enable the WebSocket output first by setting the field `pythonVisualization` to `true`:

```json
{
 "globals": {
   "deltaT": 1,
   "steps": 1000,
   "console": true,
   "pythonVisualization" : true
 }
  // ... your agent, entities and layer mappings
}
```

If the model is configured from within the `Program.cs` file, then setting the field `EnableSimpleVisualization` to `true` enables the visualization mode.

```csharp
Globals =
{
    DeltaTUnit = TimeSpanUnit.Seconds,
    Steps = 1000,
    ShowConsoleProgress = true,
    EnableSimpleVisualization = true
}
// ... your agent, entities and layer mappings
```

When you now start the simulation, die Python visualization will connect to it and show layer and agent movement.
