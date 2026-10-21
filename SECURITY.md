# Security

- Never commit affiliate codes, API keys, tokens, or `.env` files with secrets.
- Keep live affiliate overrides in a local `affiliates.yaml` (gitignored); ship only `affiliates.example.yaml`.
- Report sensitive issues privately to the repo owner on GitHub.
- Treat any HTML/API response from firm sites as untrusted input when parsing in agents.
