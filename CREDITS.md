# Credits and attribution

Continuously Casting Dashboards in this repository is a fork of the original [b0mbays/continuously_casting_dashboards](https://github.com/b0mbays/continuously_casting_dashboards) Home Assistant integration. The fork builds on the original maintainers' work and contributions from the upstream community. These credits document provenance; they do not imply that any contributor endorses this fork.

The original [MIT license](LICENSE) and its copyright notice are preserved. The upstream project's own [commit history](https://github.com/b0mbays/continuously_casting_dashboards/commits/main/), [contributors](https://github.com/b0mbays/continuously_casting_dashboards/graphs/contributors), and [pull requests](https://github.com/b0mbays/continuously_casting_dashboards/pulls?q=is%3Apr) remain authoritative records of authorship.

## Original creator and maintainer

- **[@b0mbays](https://github.com/b0mbays)** — created and maintained the original integration, including its core casting, configuration, monitoring, and subsequent upstream releases. [Original repository](https://github.com/b0mbays/continuously_casting_dashboards).

## Contributors whose PRs were merged upstream

The following community contributions are part of the upstream project's history on which this fork was based:

| Contributor | Upstream work |
| --- | --- |
| **[@0xAHA](https://github.com/0xAHA)** | Use the device's current volume when no fixed volume is provided ([#16](https://github.com/b0mbays/continuously_casting_dashboards/pull/16)); add UI configuration ([#120](https://github.com/b0mbays/continuously_casting_dashboards/pull/120)). |
| **[@dhruvb14](https://github.com/dhruvb14)** | Update HACS terminology in installation documentation ([#113](https://github.com/b0mbays/continuously_casting_dashboards/pull/113)) and document use without external access ([#114](https://github.com/b0mbays/continuously_casting_dashboards/pull/114)). |
| **[@purplefis](https://github.com/purplefis)** | Cast different dashboards to the same device at different times ([#40](https://github.com/b0mbays/continuously_casting_dashboards/pull/40)). |
| **[@jhbruhn](https://github.com/jhbruhn)** | Honour the casting delay during sleep-time checks ([#19](https://github.com/b0mbays/continuously_casting_dashboards/pull/19)). |

**Related later upstream contribution:** **[@DerRemo](https://github.com/DerRemo)** fixed the `EntityCategory` import for Home Assistant 2026.11 in upstream [#162](https://github.com/b0mbays/continuously_casting_dashboards/pull/162). That upstream PR was merged after this fork's initial divergence; the same compatibility problem was addressed in this fork's [#1](https://github.com/anaschillin/continuously_casting_dashboards/pull/1). This is an acknowledgement of parallel upstream work, not a claim that #162 was cherry-picked.

## Upstream PRs incorporated into this fork

Three upstream proposals were combined, adapted, and merged into this fork through [fork PR #1](https://github.com/anaschillin/continuously_casting_dashboards/pull/1). The original proposals were still open upstream when incorporated here:

| Original contributor | Contribution | Source |
| --- | --- | --- |
| **[@phazethru](https://github.com/phazethru)** | Optional Google TV keepalive using a Home Assistant remote entity. | [Upstream #152](https://github.com/b0mbays/continuously_casting_dashboards/pull/152) |
| **[@mrmees](https://github.com/mrmees)** | Recovery after repeated Cast status timeouts, while protecting active and recently active media. | [Upstream #153](https://github.com/b0mbays/continuously_casting_dashboards/pull/153) |
| **[@bakerboy908](https://github.com/bakerboy908)** | Detect active DashCast using the correct Home Assistant Cast `media_player` state to avoid unnecessary recasting. | [Upstream #154](https://github.com/b0mbays/continuously_casting_dashboards/pull/154) |

The combined implementation introduced additional compatibility, safety checks, tests, and integrations; it should not be treated as a verbatim merge of those three branches.

## Further work and community history

Later features and maintenance specific to this fork are documented in the [fork's pull requests](https://github.com/anaschillin/continuously_casting_dashboards/pulls?q=is%3Apr) and [commit history](https://github.com/anaschillin/continuously_casting_dashboards/commits/main/). Credit also belongs to the people who reported bugs, tested releases, and reviewed changes in the original project.

For a broader record beyond the named PR authors, see the original repository's [contributors graph](https://github.com/b0mbays/continuously_casting_dashboards/graphs/contributors) and [full pull-request history](https://github.com/b0mbays/continuously_casting_dashboards/pulls?q=is%3Apr).
