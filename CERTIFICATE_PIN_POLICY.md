# Certificate pin and renewal policy

The candidate bootstrap deliberately leaves `tlsCertificateSha256` empty. Unity continues normal operating-system CA-chain and hostname validation for `desktop-bjqavat.tailda6a70.ts.net`. This is the recommended setting for a Let's Encrypt certificate that renews under the same hostname: leaf-key rotation does not require a bootstrap update.

If a leaf pin is explicitly adopted later, set the 64-hex SHA-256 of the active leaf in the bootstrap JSON and publish the new JSON over HTTPS before clients need the replacement certificate. Verify the downloaded bytes, schema, hostname, SNI, chain and fingerprint before changing the Java keystore. Never disable CA-chain or hostname validation to make a pin work.

The running recovery client currently has an empty packaged `bootstrapUrl`; it cannot obtain remote pin updates. Production clients must first be built with the exact Pages `bootstrapUrl` and TLS required. Until then, a changed pin would require a client update. The unpinned configuration avoids this extra rotation dependency.
