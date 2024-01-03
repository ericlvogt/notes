#concept 
Zero downtime deployment strategy
Alternative to [[Rolling Deployment]]
[[Continuous Delivery (CD)]] Strategy

Application release model to gradually transfer user traffic from a previous version to a nearly identical new release both running in production. As opposed to [[Rolling Deployment]] blue green first creates a second environment before shifting the current instance to the new environment.

The old version is the blue environment and the new is green.
Once production traffic is fully transferred from blue to green then blue can stay in standby incase of rollback.

Works in a [[Micro Service Architecture]] since you can spin up a [[Container]] for blue and green then have a [[Load Balancing|Load Blancer]] to gradually switch users from connecting to blue containers to green containers.
