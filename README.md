# Aegis

Runtime validation framework for autonomous agent actions. Domain-agnostic. Transport-agnostic.

The framework is defined by an OpenAPI 3.1 specification ([`spec/openapi.yaml`](spec/openapi.yaml)).

## Design principles

- **Graduated enforcement.** Distinct outcomes with different operational semantics.
- **Domain-agnostic.** Domain-specific risk logic is provided by external evaluators and validators.
- **Transport-agnostic.** HTTP binding provided. Other transports are implementation-defined.
- **Fail-safe.** Safety invariants are normative per RFC 2119.
- **Deterministic evaluation.** Strictly ordered stages. Earlier stages may short-circuit.

## Security

- OAuth2 client credentials
- Bearer JWT
- API key
- RFC 7807 error responses
- ETag/If-Match on policy updates
- X-Request-ID on all operations

## Status

v0.1.0.

## License

Apache-2.0
