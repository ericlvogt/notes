Your code should read like plain English. 

## Be Concise
One example of a bad implementation is .NET Framework `ILogger`
To log a message you have to write something like this:
```csharp
public ILogger<MyClass> _logger;

public void LogHello()
{
	_logger.LogInfo("Hello");
}
```

Why not instead `log.Info("Hello");`

## Naming Variables
Tell don't ask
`IsVisible` better than `Visibility`

Positives over negatives
`IsVisible` or `IsCollapsed` better than `IsNotCollapsed` or `IsNotVisible`. Use the not operator instead.

Hierarchy
`ButtonColour` better than `ColourForButton`

Make plural and singular obvious
`dataEntry` and `dataEntries` better than `data` which leads to `dataRow`/`dataEntry`