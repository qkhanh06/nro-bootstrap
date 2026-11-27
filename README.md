# NRO Bootstrap metadata repository

This is a metadata-only repository draft for `qkhanh06/nro-bootstrap`. The remote repository is intended to remain private during review. It contains no game source, database dump, credentials, private key, PKCS12 keystore, or player data.

The only file intended for the eventual Pages site is `site/server-bootstrap.json`. The candidate URL is `https://qkhanh06.github.io/nro-bootstrap/server-bootstrap.json`; it is not live until an administrator enables Pages and explicitly dispatches the gated workflow.

GitHub Pages from a private repository is not itself private by default. A public Pages site is internet-accessible even if its source repository is private. Private Pages access control requires GitHub Enterprise Cloud. Verify the account's Pages plan before enabling publication.

`publish-pages.yml` runs only by manual dispatch and its publication approval input defaults to false. The Pages environment should also have a required reviewer and a main-branch deployment restriction before the workflow is used.
