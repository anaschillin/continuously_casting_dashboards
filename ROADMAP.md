# Development roadmap

This roadmap tracks planned improvements for [Continuously Casting Dashboards](https://github.com/anaschillin/continuously_casting_dashboards). Milestones are intentionally incremental: each feature PR should have regression tests and current documentation before merging.

## Baseline — completed

- [x] Merge upstream [#152](https://github.com/b0mbays/continuously_casting_dashboards/pull/152), [#153](https://github.com/b0mbays/continuously_casting_dashboards/pull/153), and [#154](https://github.com/b0mbays/continuously_casting_dashboards/pull/154) on a single branch.
- [x] Fix `EntityCategory` compatibility with Home Assistant 2026.11 ([upstream #161](https://github.com/b0mbays/continuously_casting_dashboards/issues/161)).
- [x] Add basic Python regression smoke tests and GitHub Actions.

## Milestone 1 — dashboard rules, scheduling, and volume (merged in PR #2)

**Merged:** [PR #2](https://github.com/anaschillin/continuously_casting_dashboards/pull/2) includes independent rule selection, opt-in continuous casting, volume preservation, UI persistence changes, and regression tests. Code-level checks passed; continue validating real Cast devices across HA versions.


- [x] Evaluate time and required entity state **per dashboard**. First eligible dashboard in configuration order wins; no disabled dashboard should block another eligible dashboard ([upstream #145](https://github.com/b0mbays/continuously_casting_dashboards/issues/145)).
- [x] Support an explicit **cast continuously** option for dashboards that should not use global or custom time windows ([upstream #156](https://github.com/b0mbays/continuously_casting_dashboards/issues/156)).
- [x] Support **preserve volume** so casting neither mutes nor changes existing device volume ([upstream #142](https://github.com/b0mbays/continuously_casting_dashboards/issues/142)).
- [x] Keep start/end times and new options stable when creating, editing, changing between dashboards, and saving ([upstream #144](https://github.com/b0mbays/continuously_casting_dashboards/issues/144)).
- [x] Cover multiple dashboards, overrides, custom states, midnight windows, config persistence, and opt-in volume behaviour with automated tests.
- [x] Retain compatibility: existing configs should use current time-window and volume behaviour unless a new option is explicitly enabled.

## Milestone 2 — discovery, recovery, and resource safeguards (core merged in PR #3)

**Merged:** [PR #3](https://github.com/anaschillin/continuously_casting_dashboards/pull/3) delivered discovery, bounded retries, subprocess cleanup, and diagnostic attributes. **In development:** a follow-up PR adds actionable HA Repairs and a documented CATT compatibility assessment. Hardware validation remains outstanding.

- [x] Improve reliable device name/alias matching, including Google-appended suffixes, without false-positive cross-device matches ([upstream #146](https://github.com/b0mbays/continuously_casting_dashboards/issues/146)).
- [x] Add bounded process cleanup, per-device connection backoff, and memory/resource safeguards ([upstream #139](https://github.com/b0mbays/continuously_casting_dashboards/issues/139)).
- [ ] Differentiate unreachable, idle, dashboard active, assistant activity, and user-media playback.
- [x] Surface reconnect attempts, failure reasons, and repair guidance in diagnostics.
- [ ] Complete physical-device validation of CATT dependency upgrades against Home Assistant Python versions and actual Cast hardware ([upstream #160](https://github.com/b0mbays/continuously_casting_dashboards/issues/160)).

## Milestone 3 — casting management and automation (core merged in PR #4)

**Merged:** [PR #4](https://github.com/anaschillin/continuously_casting_dashboards/pull/4) introduced priorities, rotation, temporary overrides and event debounce. **In development:** a bundled control panel, timed manual pauses and notification-persistence repair. Alternate Cast backend remains a design-only evaluation.

- [x] Event-driven refresh with debounce and limited device scans, rather than relying exclusively on polling ([upstream #159](https://github.com/b0mbays/continuously_casting_dashboards/issues/159)).
- [x] Add explicit dashboard priorities, fallback selection, and optional rotation intervals.
- [ ] Build a Home Assistant device-control view for cast/pause/resume, current dashboard, connectivity, and recent errors.
- [x] Investigate a per-device casting method selector (CATT/DashCast versus compatible HA Cast APIs).
- [ ] Resolve UI setting persistence, including notification preferences ([upstream #155](https://github.com/b0mbays/continuously_casting_dashboards/issues/155)).

## Milestone 4 — dashboard readiness and custom-card support (reporter merged in PR #5)

**Merged:** [PR #5](https://github.com/anaschillin/continuously_casting_dashboards/pull/5) provides opt-in heartbeat reporting, custom-element registration status and diagnostics. It **does not** infer that a specific Cast receiver rendered correctly, and never automatically recasts based on missing reports.

- [x] Prototype an **optional** frontend heartbeat for dashboard readiness and custom-card registration; Python cannot directly inspect rendered browser content.
- [x] Track custom-element registration separately from a successful Cast command (not proof of completed page rendering).
- [ ] Add bounded retries and actionable troubleshooting when a dashboard or JavaScript card fails to initialize.
- [ ] Test multiple devices, frontend reloads, kiosk mode, and Home Assistant version upgrades.

## Quality gates (all milestones)

1. Add automated regression tests for both expected and failure paths.
2. Run Python syntax, JSON validation, Ruff, and available integration tests in CI.
3. Verify configuration migrations, Home Assistant restart behaviour, and device isolation.
4. Keep README, translations, services, and release notes consistent.
5. Test manually on at least one Cast device before merging a high-risk runtime change.

**No target dates are assigned.** Checked items indicate implemented and covered by code-level tests; hardware and real-HA integration validation is tracked separately and remains open. See [Cast backend evaluation](docs/CAST_BACKENDS.md).
