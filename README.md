# Note

This repository is only for research purposes and does not accept further contributions.

# GQL


Twitch is now exposing a GraphQL API.

It is reachable at `https://api.twitch.tv/gql` or at `https://gql.twitch.tv/gql`. The two endpoints do not seem to show
differences.


Note that it does /not/ provide an introspection endpoint through `GET`, but you can still query the `__schema`.

The only required header is `Client-ID`. For authenticated requests, use `Authorization: OAuth <oauth_token>`.


A base dump of the schema is available in [schema.json](schema.json), generated using the official
[IntrospectionQuery](https://github.com/graphql/graphql-js/blob/master/src/utilities/introspectionQuery.js).

## Interesting tidbits

Select the base types for query and mutation:

```jq
.data.__schema.types[] | select(.name == "Query")
```

```jq
.data.__schema.types[] | select(.name == "Mutation")
```
