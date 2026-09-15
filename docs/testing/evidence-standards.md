# Evidence standards

## Claims need proof

| Claim type | Acceptable evidence |
|------------|---------------------|
| Code merged | Commit on governed branch |
| Environment updated | Runtime authority record + smoke |
| Scheduler healthy | Process config + cron last/next advancing |
| Security rule works | Negative test / denied access proof |
| No secret leakage | Scan results without printing secrets |

## Redaction

Evidence packages for public discussion must strip hosts, personal data, credentials, and tenant identifiers. See [`evidence/README.md`](../../evidence/README.md).
