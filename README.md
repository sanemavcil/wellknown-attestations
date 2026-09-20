# wellknown-attestations

A public, append-only mirror of the daily attestations published by
[Wellknown](https://wellknown.network) and their anchors in Sigstore's Rekor
transparency log.

One folder per UTC day, two files each:

- `attestation.json` — the day's signed Merkle root, exactly as
  `/api/v1/attestations/daily/{day}` served it.
- `anchor.json` — the canonical document that was hashed, the log entry, its
  inclusion proof and the signed checkpoint, exactly as
  `/api/v1/attestations/daily/{day}/anchor` served it.

These are copies of public API responses. They are mirrored here so that
verifying an anchor does not depend on wellknown.network being reachable: the
log stores a hash, and a verifier also needs the document that hash was taken
over.

Nothing here is ever overwritten. Files are only added.
