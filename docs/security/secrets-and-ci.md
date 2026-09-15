# Secrets and CI

## Rules

- Never commit live passwords, API tokens, private keys, or signing material.
- CI may reference secret **names** from the platform secret store; examples here use `SECRET_NAME` only.
- Logs and diagnostics must redact credential-bearing strings.
- Example configuration files must use obvious placeholders (`change_me`).

## Anti-patterns

- “Temporary” credentials in docs
- Copy-pasting Production `.env` into tickets
- Printing secret store values in workflow summaries
- Using real infrastructure endpoints in public examples

## Synthetic conf

See [`examples/fake-odoo.conf.example`](../../examples/fake-odoo.conf.example).
