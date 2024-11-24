Your code should read like plain English. One example of a bad implementation is .NET Framework ILogger

To log a message you have to write something like this:
```csharp
public ILogger<MyClass> _logger;

public void LogHello()
{
	_logger.LogInfo("Hello");
}
```

Why not instead `log.Info("Hello");`