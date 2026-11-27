# GitHub Pages publication procedure (not activated)

Candidate URL: `https://qkhanh06.github.io/nro-bootstrap/server-bootstrap.json`.

The repository is private and Pages is not configured or published. A private repository does not make its Pages site private: public Pages from private repository source are accessible on the internet. Private Pages access control requires GitHub Enterprise Cloud. Verify plan eligibility and approve the public metadata before enabling Pages.

After the safety review:

1. Configure a `github-pages` environment with a required reviewer and restrict deployments to the default branch.
2. In repository Settings → Pages, select GitHub Actions as the publishing source and require HTTPS.
3. Confirm the reviewed endpoint, port 443, SNI and TLS certificate behavior. The candidate pin is intentionally empty, so standard CA and hostname checks remain active.
4. Manually dispatch `Publish Bootstrap` and explicitly set `publication_approved=true` only after approval.
5. Verify the final URL returns HTTP 200 over HTTPS, no redirect downgrade, JSON content type, schema-valid content and the exact expected SHA-256. Confirm downloaded bytes equal `site/server-bootstrap.json`.
6. Update the production Windows and Android client bootstrap URLs only after endpoint and platform testing. The current recovery client is LOCAL-only apart from this controlled TLS test.

No Pages API configuration or deployment has been performed as part of staging.
