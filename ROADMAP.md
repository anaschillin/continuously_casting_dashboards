# Development roadmap

This roadmap lists **future work and remaining validation** for [Continuously Casting Dashboards](https://github.com/anaschillin/continuously_casting_dashboards). Completed work belongs in the [changelog](CHANGELOG.md) and merged [pull-request history](https://github.com/anaschillin/continuously_casting_dashboards/pulls?q=is%3Apr+is%3Amerged), not in this list.

The current merged integration metadata is **3.0.3**, with `catt==0.13.3`. This is not a statement that a tagged GitHub release exists or that every device has been validated.

## Receiver compatibility and reliability

- [ ] Validate v3.0.3 on HAOS and real Cast receivers, including Nest Hub/Chromecast models, dashboard loading, startup, restart/reload, multiple devices, and intermittent network failure.
- [ ] Exercise `catt==0.13.3` on real hardware: direct IP and name discovery, DashCast status, dashboard URLs, volume preservation, user media/Assistant protection, group playback, recovery and stop semantics. Automated CLI compatibility tests are not substitutes.
- [ ] Validate the **opt-in** custom-card guard and receiver diagnostics on panel and ordinary Lovelace views, multiple third-party cards, resource failures, authentication failures and deliberately invalid cards.
- [ ] Confirm the reported `cast_frontend` states on a physical receiver; `no_report` is inconclusive, and observations may originate from another browser opening the same guarded URL.
- [ ] Continue tracking Home Assistant frontend resource/registry races and avoid presenting the CCD guard as a frontend core fix.

## Future features and investigation

- [ ] Investigate reliable, receiver-specific frontend confirmation that goes beyond custom-element registration or an unauthenticated browser identity.
- [ ] Explore safe, bounded handling of missing resources or frontend heartbeat failures without automatically recasting or interrupting user media.
- [ ] Evaluate an **opt-in** native Home Assistant Cast backend as an alternative to CATT/DashCast, with separate compatibility and media-protection checks. See [backend assessment](docs/CAST_BACKENDS.md); no such backend is implemented.

## Quality, documentation and releases

- [ ] Expand integration tests to a running Home Assistant environment, covering YAML migration, options flow, service contracts, unload/restart and multi-device isolation.
- [ ] Extend Ruff coverage to older modules as they are cleaned up, and retain Python, JavaScript, translations, version-consistency and CATT CLI checks.
- [ ] Publish a tagged version only after release checks and available receiver validation; verify Marketplace update availability independently from version metadata.
- [ ] Keep README, upgrade help, changelog, Marketplace metadata, services, test coverage and upstream attribution current.

Items are unchecked until the indicated work or validation is complete. For current setup see the [README](README.md); for troubleshooting and rollback see the [upgrade guide](docs/update_help.md).
