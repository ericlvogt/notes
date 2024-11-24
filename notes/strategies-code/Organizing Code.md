There are a few methods of organizing code that truly make a difference. Understand their tradeoffs and choose wisely. This is organized from most important to least important.

## By Teams
*The more control a team has over their own responsibilities the better*
Microservices was developed to separate concerns by individuals or teams of people. Developers so often apply this as a technical strategy when it was created as a social strategy intended to separate concerns by teams and establish concrete interfaces between teams. This means each team has autonomy to do what they want under the hood.

For team happiness we should make sure we separate code by team to make sure each team feels the freedom to modify their implementation as much as they want. They don't have to slow down to change what they are responsible for because another team controls part of what they do.

Interfaces between teams should be as simple as possible. Reduce the complexity of interfaces between teams since this adds more technical debt and requires more maintenance and communication between teams.

## By Applications
**

## By Dependencies
*The less dependencies the better*
One goal all projects should have is to reduce dependencies on any external code. This means any code external to the repository it is developed in. We should treat any dependencies like the plague since they can add significant technical debt. We have to continuously update dependencies each additional dependency can cause issues like if one dep is no longer maintained or if one clashes with another one's upgrade. 

Frameworks and SDKs are worst of all make sure these are used to the minimum since they so thoroughly spread across your code base. Choose frameworks wisely since changing from one framework to another takes a significant effort.

For libs use the adapter pattern to avoid the spread of external interfaces throughout your code base. Keep adapters specific to purpose. It's okay if you have to adapt a library multiple times to avoid dependencies between completely isolated applications:

Ex. If you have an application that requires you to send HTTP requests to a REST server (calling this PRIME) and another requiring you to send HTTP requests to Azure its not a bad idea to create multiple adapters like `PrimeClient` and `AzureClient`. Avoid `HttpClient` since you either end up with multiple `HttpClient` implementations or you create dependencies between PRIME requests and Azure requests and changing may break one or the other. Additionally, now if you have to move away from the HTTP library it would require doing both at the same time or a refactor to split to 2 adapters prior to the update. Let library maintainers handle generic implementations.

If you simply must create generic implementations keep them simple as possible. Each line of code is significant technical debt.

## By Frequency of Changes
*The less you have to rebuild per change the better*
More important for compiled languages but to keep build times low we should make sure the code that is most in flux has the least dependencies on it. This lends well to Application - depends on -> Infrastructure - depends on -> Models project layout since Models change more rarely than infrastructure (clients and adapters) implementations change more rarely than application (business logic, ui implementation, etc.).