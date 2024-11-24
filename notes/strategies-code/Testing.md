*The closer your test environment is to the prod environment the better*
## What to Test
Tests should capture the original requirements and any complex behaviours. Test at public interfaces. If you are having to expose interfaces just to test consider if the scope you are testing is too dependent on the implementation.
## Mocking
Mocking is largely useless. It is far more valuable to test with the actual implementations. Try only mock to test error cases.
## Seams
You want to create seams where you can use mocks when you don't have that service available. It also allows you to test error states like what happens if you can't actually connect to the internet. Or what if that service throws an error in the middle of reading from the server. This is where you should use dependency injection.