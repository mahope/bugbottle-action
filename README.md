# Bugbottle Report Validator (GitHub Action)

Validate bug reports collected by [bugbottle](https://github.com/mahope/bugbottle)
inside a CI workflow — e.g. reports exported from your endpoint as JSON files in
the repository or an artifact. Fails the job when a report is malformed, so bad
data never reaches your issue tracker.

## Usage

```yaml
- uses: mahope/bugbottle-action@v1
  with:
    reports-glob: "reports/*.json"     # required
    require-screenshot: false          # fail reports without a screenshot
    max-report-size-kb: 4096           # reject oversized report files
```

Outputs `valid-count` and `invalid-count`. The job fails if any report is
malformed or no files match. Zero dependencies — installs in about a second.

## Inputs

| Input | Required | Default | Description |
|-------|----------|---------|-------------|
| `reports-glob` | yes | — | Glob pattern for JSON report files to validate |
| `require-screenshot` | no | `false` | Fail reports that carry no screenshot |
| `max-report-size-kb` | no | `4096` | Fail any single report file larger than this |

## Related

- [bugbottle](https://github.com/mahope/bugbottle) — the in-app collector that produces the reports this action validates; product page at [bugbottle.dev](https://bugbottle.dev/)
- [Live demo](https://mahope.tools/bugbottle-demo.html) — see what a collected report looks like
- [Clean Copy CLI](https://github.com/mahope/clean-copy-cli) and other free tools at [mahope.tools/free-tools](https://mahope.tools/free-tools)

## License

MIT — same as the bugbottle library.

## Author

Built by Mads Holst Jensen — developer and technical partner for small businesses, Odense, Denmark. https://mahoje.dk
