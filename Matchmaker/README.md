# Pixel Streaming Matchmaker

Instead of having all users connect to the same stream, you may want each person to end up in their own interactive experiences. To do this, you can run a separate stack of Pixel Streaming components for each user, and direct each user to a separate Signaling and Web Server to start a connection.

You can set up each stack of Pixel Streaming components on a separate host, or you can put more than one stack on the same host as long as you configure the port settings for the components within each stack so that they all communicate over different ports. See the Pixel Streaming Reference for details on these port settings.

To help set up this kind of configuration, the Pixel Streaming system can use a **matchmaker** server that tracks which Signaling and Web Servers are available, and whether they are being used by a client connection.


## Docs
- [Hosting and Networking Guide](https://docs.unrealengine.com/5.1/en-US/hosting-and-networking-guide-for-pixel-streaming-in-unreal-engine/)
- [Customizing the Queue UI](Docs/Customizing%20the%20Queue%20UI.md)

# Authentication

Add authentication to the endpoints `:9090/` and `:9090/signallingserver`

Validate Cognito bearer tokens using passport strategy

If token is invalid or expired a 401 is returned

the authentication is enabled with the feature flag COGNITO_AUTH_ENABLED="true"

the project now needs a file `.env` inside the Matchmaker folder with these values:

```
COGNITO_USER_POOL_ID="cognito user pool id "
COGNITO_CLIENT_ID="cognito client id"
COGNITO_REGION="us-west-2"
COGNITO_AUTH_ENABLED="false"
```