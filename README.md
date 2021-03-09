# env

> Use `.env` files in your Unity projects.

### Unity Package Manager

<https://docs.unity3d.com/Packages/com.unity.package-manager-ui@2.0/manual/index.html>

#### Git

```json
{
  "dependencies": {
    "xyz.candycoded.env": "https://github.com/CandyCoded/env.git#v1.0.0",
    ...
  }
}
```

## Usage

Create a `.env` file at the root of your project, outside of the `Assets/` folder, and paste the following content:

```
DEBUG=true
```

> Note: Don't forget to add `.env` to your `.gitignore` file before committing any changes!

Now you can reference the variables and their values with the key specified in the `.env` file. Supported value types
are `string`, `bool`, `double`, `float`, and `int`.

```csharp
if (env.TryParseEnvironmentVariable("DEBUG", out bool isDebug))
{
    Debug.Log($"Debug Mode is: {(isDebug ? "ON" : "OFF")}");
}
```