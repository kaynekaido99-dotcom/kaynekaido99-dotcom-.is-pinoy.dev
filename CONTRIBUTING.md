# Contributing

Thanks for wanting to register a subdomain or improve this project!

## Registering a Subdomain

### 1. Fork the repository

Click **Fork** on GitHub and clone your fork locally.

### 2. Create your subdomain file

Add a file at `subdomains/<your-subdomain>.json`. The filename must match the `subdomain` field exactly.

```json
{
  "subdomain": "yourname",
  "owner": {
    "github": "your-github-username"
  },
  "records": {
    "CNAME": {
      "value": "yoursite.vercel.app."
    }
  }
}
```

### 3. Validate locally (optional)

If you have the CLI available:

```bash
npx @is-pinoy/cli registry validate --dir ./subdomains
```

### 4. Open a pull request

Submit your PR from your fork to the `main` branch. The CI will validate your file automatically. A maintainer will review and merge it — your subdomain goes live shortly after.

## Naming Rules

- Lowercase alphanumeric and hyphens only: `a-z`, `0-9`, `-`
- Between 1 and 63 characters
- No leading or trailing hyphens

## What Gets Rejected

- **Squatting** — registering a subdomain you don't intend to use
- **Impersonation** — using someone else's name or brand
- **Invalid records** — values that don't pass schema validation
- **Mismatched owner** — `owner.github` must match the GitHub account opening the PR
- **Reserved names** — certain subdomains are reserved by maintainers

## After Your PR is Merged

DNS changes are synced to Cloudflare automatically. Propagation typically takes a few minutes but can take up to 48 hours depending on your resolver.

## Reporting Issues

Open a GitHub issue for bugs, questions, or requests to update/remove a subdomain.
