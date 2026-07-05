# Aegis

Runtime validation framework for autonomous AI agent decisions. Intercepts inference outputs before execution, evaluates criticality, and applies graduated validation proportional to risk.

The framework is defined by an OpenAPI 3.1 specification ([`spec/openapi.yaml`](spec/openapi.yaml)).

## Research

This framework implements the Guard Rail Validation (GRV) architecture described in:

> R. K. Sharma, "Criticality-Based Guard Rail Validation for AI Agent Decisions in Autonomous Telecom Networks," arXiv:2607.02210, July 2026.

[Read the paper (PDF)](https://arxiv.org/pdf/2607.02210)

## Key Capabilities

| Capability | Description |
|-----------|-------------|
| Multi-dimensional criticality evaluation | Scores decisions across action scope, type, service criticality, autonomy level, reversibility, and temporal patterns |
| Graduated validation | LOW (log), MEDIUM (bounds check), HIGH (independent validator), CRITICAL (M-of-N consensus) |
| Cross-agent conflict detection | Detects contradictory decisions from multiple agents targeting the same entity |
| Temporal pattern detection | Identifies oscillation, burst, and frequency anomalies in agent behavior |
| Conformance logging | Structured audit trail satisfying EU AI Act Article 14 and NIST AI RMF |

## Design Principles

- **Graduated enforcement.** Qualitatively different validation mechanisms per criticality level.
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

v0.1.0 - OpenAPI specification complete. Python implementation planned.

## License

Apache-2.0
