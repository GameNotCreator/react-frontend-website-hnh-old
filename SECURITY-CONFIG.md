# Private configuration

Committed credentials were removed from the current source on 2026-10-28. The old values may remain in Git history or other copies; removing them from the latest files does not revoke them.

Set the following values in the runtime environment before starting the application:

- `SMTP_PASSWORD`
- `SMTP_USER`
- `MONGODB_URI`
- `SESSION_SECRET`

These values are read from `process.env`. This change does not add a dotenv dependency: set variables in the shell, service manager or deployment settings before starting the existing application command. An `.env.example` is a list of keys, not an automatically loaded configuration file.

Rotate or revoke exposed service credentials with their providers. Keep encryption-key migration and session invalidation in mind. The application, database access, mail delivery or bot login may remain unavailable until configuration is supplied. No live credentials were tested, and no services were accessed as part of this change.
