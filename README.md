# ECZ-ID Supply Chain Evidence

Organize existing SBOM, package, lockfile, provenance and machine-identity evidence without generating SBOMs, attestations or vulnerability scores.

## Outcome

Normalize software supply-chain identity/evidence while consuming, not replacing, GitHub-native provenance.

## Quick start

```yaml
- uses: EcoCitizenz-Ltd/eczid-supply-chain-evidence@v1
  with:
    family: sdk
```

## Inputs

| Input | Required | Default | Description |
|---|---:|---|---|
| `family` | No | — | Optional plugin \| sdk \| service-workload hint for the free Passport route. |
| `provenance-status` | No | `NOT_CHECKED` | VERIFIED \| NOT_VERIFIED \| NOT_CHECKED \| NOT_AVAILABLE. |
| `sbom-status` | No | `NOT_CHECKED` | VERIFIED \| NOT_VERIFIED \| NOT_CHECKED \| NOT_AVAILABLE. |
| `report-path` | No | `eczid-supply-chain-evidence.json` | Path for the local JSON evidence report. |

## Outputs

| Output | Description |
|---|---|
| `result-state` | NOT_APPLICABLE, OBSERVED or REVIEW_RECOMMENDED. |
| `sbom-count` | Observed SBOM count. |
| `package-count` | Observed package identity count. |
| `lockfile-count` | Observed lockfile count. |
| `next-action` | One neutral next action. |
| `next-action-url` | Free Passport/Resolver route when applicable. |
| `reason-codes` | Deterministic reason-code list. |
| `report-path` | Generated local JSON report path. |

## Permissions, secrets and data

- The Action itself does not require repository write permission.
- No ECZ-ID secret or API key is required for this public Action.
- Supported declarations/manifests are read locally inside the GitHub Actions workspace; repository source and evidence documents are not uploaded to ECZ-ID.
- See [PRIVACY.md](./PRIVACY.md), [SECURITY.md](./SECURITY.md) and [SUPPORT.md](./SUPPORT.md) for the complete public boundary.

## Version pinning

The examples use the stable `@v1` compatibility tag. For policies that require an immutable third-party reference, pin this Action to the full commit SHA of the reviewed release. GitHub Actions does not support action-name redirects as a substitute for a stable reference.

## Trust boundary

- Bounded deterministic evidence/current-state processing.
- No hidden telemetry.
- No repository code execution.
- Missing ECZ-ID or missing evidence never means unsafe, non-compliant or untrusted.
- No automatic ownership inference.
- No pay-to-pass.
- No global safety/certification/compliance/approval verdict.
- Local policy decides.

## ECZ-ID identity model

A free Declared Business Passport is the organisation Parent gateway for the seven free machine Passport families: Agent, MCP, Plugin, API, IoT / Device, SDK, and Service & Workload. Verified or Assured strengthens the same Parent ECZ-ID; it does not automatically independently verify a child Passport.

When an identity/currentness next step is warranted, ECZ-ID returns at most one neutral route. Payment never changes the technical result.

## Works with GitHub, not against it

ECZ-ID complements GitHub-native controls with persistent identity, accountable operator context, declared authority, current state, change and re-checkable evidence. It does not replace CodeQL, secret scanning, dependency review, workflow dependency lockfiles or artifact attestations.

## Support and security

Use the repository issue tracker only for reproducible product defects that contain no secrets or customer-private evidence. Follow [SECURITY.md](./SECURITY.md) for vulnerability reporting and [SUPPORT.md](./SUPPORT.md) for private/commercial support routes.
