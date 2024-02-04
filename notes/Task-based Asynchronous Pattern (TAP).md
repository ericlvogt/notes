#architecture-pattern 
[[_.NET]] guides how to implement asynchronous logic.

There are 2 different patterns with async:

```cs
// Only use async void to subscribe to events
// OnClick should subscribe to the Click event
private async void OnClick()
{
	// This will execute as a single thread
	// Use when the task is IO bound (has to wait for a response)
	await ReadSomeData();

	// This will execute on a separate thread
	// Use when the task is CPU bound (lots of processing will freeze the main thread)
	await Task.Run(() => CalculateSomething());
}

private async Task ReadSomeData()
{
	// The context of the await call will be stored while the thread is inactive
	// The thread will be free to handle other tasks during this time
	await Task.Delay(1000);
	
	// While waiting for the IO to return the thread will be free to handle other tasks
	await ReadFromDatabase(timeout=20_000);
	await HttpRequest(timeout=20_000);
}

private void CalculateSomething()
{
	// Thread is dedicated to computation. Would seize thread if not run
	// in parallel
	SomeHeavyCalculation();
}

```