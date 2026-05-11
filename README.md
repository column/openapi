# Column OpenAPI

This repository contains Column's OpenAPI specification.

The spec describes the Column API surface exposed at `https://api.column.com/`. Use it to generate API clients, import Column endpoints into API tooling, validate request and response shapes, or build local mocks for integration testing.

## Files

- `openapi.yaml` - OpenAPI 3.1 specification for the Column API.

## API Documentation

The OpenAPI spec is a machine-readable reference. For narrative guides, API examples, and product documentation, see [docs.column.com](https://docs.column.com).

## API Basics

Column uses HTTP Basic Auth. Use your API key as the password and leave the username blank:

```sh
curl -u :<YOUR_API_KEY> https://api.column.com
```

Sandbox and production requests use the same API domain. Sandbox keys are prefixed with `test_`; production keys are prefixed with `live_`.

## Using the Spec

You can use any OpenAPI-compatible tool with `openapi.yaml`.

Preview the API reference locally:

```sh
npx @redocly/cli preview-docs openapi.yaml
```

Generate a client SDK:

```sh
npx @openapitools/openapi-generator-cli generate \
  -i openapi.yaml \
  -g typescript-fetch \
  -o ./generated/column
```

Replace `typescript-fetch` with another generator name to produce a client for your preferred language.