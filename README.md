# GQL

Twitch is now exposing a GraphQL API.

It is reachable at `https://api.twitch.tv/gql` or at `https://gql.twitch.tv/gql`. The two endpoints do not seem to show
differences.


Note that it does /not/ provide an introspection endpoint through `GET`, but you can still query the `__schema`.

The only required header is `Client-ID`. For authenticated requests, use `Authorization: OAuth <oauth_token>`.
