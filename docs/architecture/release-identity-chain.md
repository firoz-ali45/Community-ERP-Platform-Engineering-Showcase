# Release identity chain

## Goal

Answer: “What exact software is running?” without trusting chat history.

## Five layers

1. **Source** — files on the governed branch.
2. **Commit** — immutable Git object identity.
3. **Pushed tip** — remote agreement with local tip.
4. **Promoted release** — the commit authorized into an environment.
5. **Runtime authority** — environment-side record stating which release is mounted/active.

## Invariant

Claims that “Sandbox is fixed” require layers 4–5, not only layer 2–3.

## Synthetic illustration

See [`examples/fake-release-latest.json.example`](../../examples/fake-release-latest.json.example). Values are fictional.
