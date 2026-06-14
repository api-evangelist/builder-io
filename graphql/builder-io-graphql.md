# Builder.io GraphQL API

Builder.io exposes a public GraphQL Content API that enables type-safe queries against your Builder.io space's content models. The API is schema-driven: every content model defined in your Builder space automatically generates a corresponding GraphQL type, a list query field (e.g. `page`, `blogArticle`), and a single-item query field (e.g. `onePage`, `oneBlogArticle`). All content entry types share a common set of metadata fields (`id`, `name`, `ownerId`, `modelId`, `published`, `createdDate`, `lastUpdated`, and `query`) alongside a model-specific `data` object that contains the custom fields you define in the Builder visual editor.

Authentication for read-only public content queries is handled via your public API key embedded in the endpoint URL path — no Authorization header is required for published content. Filtering and pagination are performed through the `query` argument (MongoDB-style JSON filter), `limit`, `offset`, and `sort` arguments. Targeting by user attributes (device, URL, locale, custom attributes) is supported via the `target` argument. An interactive GraphQL Explorer is available in the Builder.io dashboard to browse your space's generated schema and test queries live.

The endpoint URL takes the form `https://cdn.builder.io/api/v3/graphql/{yourPublicApiKey}`, where `yourPublicApiKey` is the public key found in your Builder.io space settings. Both GET and POST HTTP methods are accepted for queries. GET requests pass the query as a URL parameter; POST requests send a standard `application/json` body with a `query` field. The API supports all standard GraphQL introspection, making it compatible with any GraphQL client or IDE (GraphiQL, Apollo Studio, Insomnia, etc.).

**Endpoint:** https://cdn.builder.io/api/v3/graphql/{yourPublicApiKey}

**Documentation:** https://www.builder.io/c/docs/graphql-api

**References:**
- Documentation: https://www.builder.io/c/docs/graphql-api
- GettingStarted: https://www.builder.io/c/docs/intro-to-builder-apis
