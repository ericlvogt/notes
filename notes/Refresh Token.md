#concept
Authorization server issues this to a client to allow a client to request a new [[Access Token]] from an authorization server.

Refresh token rotation is creating new refresh token each time a new access token is issued

[[Bearer Token]]

Used in [[OAuth]]

If an old refresh token is used then we should invalidate all refresh token family and require the user to relog in.