# Source Snapshot: Patch Releases

- **Accessed:** 2026-10-19
- **Type:** official documentation (Kubernetes Docs)
- **URL:** https://kubernetes.io/releases/patch-releases/
- **Upstream file:** [`kubernetes/website` → `content/en/releases/patch-releases.md`](https://github.com/kubernetes/website/blob/1fc565c2f557823a911f073dc577945230f27dd7/content/en/releases/patch-releases.md) at commit `1fc565c` (2026-10-19)
- **License:** Creative Commons Attribution 4.0 International (CC BY 4.0) — Copyright The Kubernetes Authors ("Documentation Distributed under CC BY 4.0"). See [LICENSE-kubernetes-website](LICENSE-kubernetes-website). Reproduced verbatim and unmodified below this line.
- **Included files:** the published page pulls these files in when the site is built (code samples, shared includes, partials). They are appended verbatim after the page, under "Included files", from the same commit: [`data/releases/schedule.yaml`](https://github.com/kubernetes/website/blob/1fc565c2f557823a911f073dc577945230f27dd7/data/releases/schedule.yaml); [`data/releases/eol.yaml`](https://github.com/kubernetes/website/blob/1fc565c2f557823a911f073dc577945230f27dd7/data/releases/eol.yaml)
- **Release data:** the release tables on this page are rendered by shortcodes (`release-data`, `upcoming-releases`, `eol-releases`, `release-branches`, `skew currentPatchVersion`) from the `data/releases/*.yaml` files listed under Included files.

---

---
title: Patch Releases
type: docs
---

Schedule and team contact information for Kubernetes patch releases.

For general information about Kubernetes release cycle, see the
[release process description].

## Cadence

Our typical patch release cadence is monthly. It is
commonly a bit faster (1 to 2 weeks) for the earliest patch releases
after a 1.X minor release. Critical bug fixes may cause a more
immediate release outside of the normal cadence. We also aim to not make
releases during major holiday periods.

## Contact

See the [Release Managers page][release-managers] for full contact details on the Patch Release Team.

Please give us a business day to respond - we may be in a different timezone!

In between releases the team is looking at incoming cherry pick
requests on a weekly basis. The team will get in touch with
submitters via GitHub PR, SIG channels in Slack, and direct messages
in Slack and [email](mailto:release-managers-private@kubernetes.io)
if there are questions on the PR.

## Cherry picks

Please follow the [cherry pick process][cherry-picks].

Cherry picks must be merge-ready in GitHub with proper labels (e.g.,
`approved`, `lgtm`, `release-note`) and passing CI tests ahead of the
cherry pick deadline. This is typically two days before the target
release, but may be more. Earlier PR readiness is better, as we
need time to get CI signal after merging your cherry picks ahead
of the actual release.

Cherry pick PRs which miss merge criteria will be carried over and tracked
for the next patch release.

## Support Period

In accordance with the [yearly support KEP][yearly-support], the Kubernetes
Community will support active patch release series for a period of roughly
fourteen (14) months.

The first twelve months of this timeframe will be considered the standard
period.

Towards the end of the twelve month, the following will happen:

- [Release Managers][release-managers] will cut a release
- The patch release series will enter maintenance mode

During the two-month maintenance mode period, Release Managers may cut
additional maintenance releases to resolve:

- [Vulnerabilities](/docs/reference/issues-security/official-cve-feed/) that have an assigned
  CVE ID (under the advisement of the Security Response Committee)
- dependency issues (including base image updates)
- critical core component issues

At the end of the two-month maintenance mode period, the patch release series
will be considered EOL (end of life) and cherry picks to the associated branch
are to be closed soon afterwards.

Note that the 28th of the month was chosen for maintenance mode and EOL target
dates for simplicity (every month has it).

## Upcoming Monthly Releases

Timelines may vary with the severity of bug fixes, but for easier planning we
will target the following monthly release points. Unplanned, critical
releases may also occur in between these.

{{< upcoming-releases >}}

## Detailed Release History for Active Branches

{{< release-branches >}}

## Non-Active Branch history

These releases are no longer supported.

{{< eol-releases >}}

[cherry-picks]: https://github.com/kubernetes/community/blob/main/contributors/devel/sig-release/cherry-picks.md
[release-managers]: /releases/release-managers
[release process description]: /releases/release
[yearly-support]: https://git.k8s.io/enhancements/keps/sig-release/1498-kubernetes-yearly-support-period/README.md

---

## Included files

### `data/releases/schedule.yaml`

````yaml
# Use "schedule-builder" to maintain this file:
# https://github.com/kubernetes/release/tree/master/cmd/schedule-builder
# For example by running:
# schedule-builder -uc data/releases/schedule.yaml -e data/releases/eol.yaml
---
schedules:
- endOfLifeDate: "2027-10-28"
  maintenanceModeStartDate: "2027-08-28"
  next:
    cherryPickDeadline: "2026-10-09"
    release: 1.37.2
    targetDate: "2026-10-13"
  previousPatches:
  - cherryPickDeadline: "2026-09-11"
    release: 1.37.1
    targetDate: "2026-09-15"
  release: "1.37"
  releaseDate: "2026-08-26"
- endOfLifeDate: "2027-06-28"
  maintenanceModeStartDate: "2027-04-28"
  next:
    cherryPickDeadline: "2026-10-09"
    release: 1.36.6
    targetDate: "2026-10-13"
  previousPatches:
  - cherryPickDeadline: "2026-09-11"
    release: 1.36.5
    targetDate: "2026-09-15"
  - cherryPickDeadline: "2026-08-07"
    release: 1.36.4
    targetDate: "2026-08-11"
  - cherryPickDeadline: "2026-07-10"
    release: 1.36.3
    targetDate: "2026-07-14"
  - cherryPickDeadline: "2026-06-05"
    release: 1.36.2
    targetDate: "2026-06-09"
  - cherryPickDeadline: "2026-05-08"
    release: 1.36.1
    targetDate: "2026-05-13"
  release: "1.36"
  releaseDate: "2026-04-22"
- endOfLifeDate: "2027-02-28"
  maintenanceModeStartDate: "2026-12-28"
  next:
    cherryPickDeadline: "2026-10-09"
    release: 1.35.10
    targetDate: "2026-10-13"
  previousPatches:
  - cherryPickDeadline: "2026-09-11"
    release: 1.35.9
    targetDate: "2026-09-15"
  - cherryPickDeadline: "2026-08-07"
    release: 1.35.8
    targetDate: "2026-08-11"
  - cherryPickDeadline: "2026-07-10"
    release: 1.35.7
    targetDate: "2026-07-14"
  - cherryPickDeadline: "2026-06-05"
    release: 1.35.6
    targetDate: "2026-06-09"
  - cherryPickDeadline: "2026-05-08"
    release: 1.35.5
    targetDate: "2026-05-12"
  - cherryPickDeadline: "2026-04-10"
    release: 1.35.4
    targetDate: "2026-04-14"
  - cherryPickDeadline: "2026-03-13"
    release: 1.35.3
    targetDate: "2026-03-19"
  - cherryPickDeadline: "2026-02-26"
    note: Out of band patch release to pick up a new version of Go to [address several
      Go CVEs](https://groups.google.com/g/golang-dev/c/ytMTMwK7QBk/m/hpcstrxADwAJ).
      No other changes.
    release: 1.35.2
    targetDate: "2026-02-26"
  - cherryPickDeadline: "2026-02-06"
    note: January 2026 patches consolidated with February
    release: 1.35.1
    targetDate: "2026-02-10"
  release: "1.35"
  releaseDate: "2025-12-17"
- endOfLifeDate: "2026-10-27"
  maintenanceModeStartDate: "2026-08-27"
  next:
    cherryPickDeadline: "2026-10-09"
    release: 1.34.13
    targetDate: "2026-10-13"
  previousPatches:
  - cherryPickDeadline: "2026-09-11"
    release: 1.34.12
    targetDate: "2026-09-15"
  - cherryPickDeadline: "2026-08-07"
    release: 1.34.11
    targetDate: "2026-08-11"
  - cherryPickDeadline: "2026-07-10"
    release: 1.34.10
    targetDate: "2026-07-14"
  - cherryPickDeadline: "2026-06-05"
    release: 1.34.9
    targetDate: "2026-06-09"
  - cherryPickDeadline: "2026-05-08"
    release: 1.34.8
    targetDate: "2026-05-12"
  - cherryPickDeadline: "2026-04-10"
    release: 1.34.7
    targetDate: "2026-04-14"
  - cherryPickDeadline: "2026-03-13"
    release: 1.34.6
    targetDate: "2026-03-19"
  - cherryPickDeadline: "2026-02-26"
    note: Out of band patch release to pick up a new version of Go to [address several
      Go CVEs](https://groups.google.com/g/golang-dev/c/ytMTMwK7QBk/m/hpcstrxADwAJ).
      No other changes.
    release: 1.34.5
    targetDate: "2026-02-26"
  - cherryPickDeadline: "2026-02-06"
    note: January 2026 patches consolidated with February
    release: 1.34.4
    targetDate: "2026-02-10"
  - cherryPickDeadline: "2025-12-05"
    release: 1.34.3
    targetDate: "2025-12-09"
  - cherryPickDeadline: "2025-11-07"
    note: October 2025 patches consolidated with November
    release: 1.34.2
    targetDate: "2025-11-11"
  - cherryPickDeadline: "2025-09-05"
    release: 1.34.1
    targetDate: "2025-09-09"
  release: "1.34"
  releaseDate: "2025-08-27"
upcoming_releases:
- cherryPickDeadline: "2026-10-09"
  targetDate: "2026-10-13"
- cherryPickDeadline: "2026-11-06"
  targetDate: "2026-11-10"
- cherryPickDeadline: "2026-12-11"
  targetDate: "2026-12-15"
- cherryPickDeadline: "2027-01-08"
  targetDate: "2027-01-12"
````

### `data/releases/eol.yaml`

````yaml
# Use "schedule-builder" to maintain this file:
# https://github.com/kubernetes/release/tree/master/cmd/schedule-builder
# For example by running:
# schedule-builder -uc data/releases/schedule.yaml -e data/releases/eol.yaml
---
branches:
- endOfLifeDate: "2026-06-28"
  finalPatchRelease: 1.33.13
  release: "1.33"
- endOfLifeDate: "2026-02-28"
  finalPatchRelease: 1.32.13
  release: "1.32"
- endOfLifeDate: "2025-11-11"
  finalPatchRelease: 1.31.14
  release: "1.31"
- endOfLifeDate: "2025-07-15"
  finalPatchRelease: 1.30.14
  release: "1.30"
- endOfLifeDate: "2025-02-28"
  finalPatchRelease: 1.29.14
  release: "1.29"
- endOfLifeDate: "2024-10-22"
  finalPatchRelease: 1.28.15
  release: "1.28"
- endOfLifeDate: "2024-07-16"
  finalPatchRelease: 1.27.16
  release: "1.27"
- endOfLifeDate: "2024-02-28"
  finalPatchRelease: 1.26.15
  note: 1.26.15 was released in March 2024 (after the EOL date) to pick up a new version
    of Go to [address several Go CVEs](https://groups.google.com/g/golang-dev/c/o1I1Vv8Rfgs/m/Wr8tD1RlAgAJ)
  release: "1.26"
- endOfLifeDate: "2023-10-28"
  finalPatchRelease: 1.25.16
  note: 1.25.16 was released in November 2023 (after the EOL date) to fix [CVE-2023-5528](https://groups.google.com/g/kubernetes-announce/c/c3py6Fw0DTI/m/cScFSdk1BwAJ)
  release: "1.25"
- endOfLifeDate: "2023-07-28"
  finalPatchRelease: 1.24.17
  note: 1.24.17 was released in August 2023 (after the EOL date) to fix CVE-2023-3676
    and CVE-2023-3955
  release: "1.24"
- endOfLifeDate: "2023-02-28"
  finalPatchRelease: 1.23.17
  release: "1.23"
- endOfLifeDate: "2022-12-08"
  finalPatchRelease: 1.22.17
  note: 1.22.17 was released in December 2022 (after the EOL date) to backport registry
    changes and fix two critical issues.
  release: "1.22"
- endOfLifeDate: "2022-06-28"
  finalPatchRelease: 1.21.14
  release: "1.21"
- endOfLifeDate: "2022-02-28"
  finalPatchRelease: 1.20.15
  release: "1.20"
- endOfLifeDate: "2021-10-28"
  finalPatchRelease: 1.19.16
  release: "1.19"
- endOfLifeDate: "2021-06-18"
  finalPatchRelease: 1.18.20
  note: Created to solve regression introduced in 1.18.19
  release: "1.18"
- endOfLifeDate: "2021-01-13"
  finalPatchRelease: 1.17.17
  release: "1.17"
- endOfLifeDate: "2020-09-02"
  finalPatchRelease: 1.16.15
  release: "1.16"
- endOfLifeDate: "2020-05-06"
  finalPatchRelease: 1.15.12
  release: "1.15"
- endOfLifeDate: "2019-12-11"
  finalPatchRelease: 1.14.10
  release: "1.14"
- endOfLifeDate: "2019-10-15"
  finalPatchRelease: 1.13.12
  release: "1.13"
- endOfLifeDate: "2019-07-08"
  finalPatchRelease: 1.12.10
  release: "1.12"
- endOfLifeDate: "2019-05-01"
  finalPatchRelease: 1.11.10
  release: "1.11"
- endOfLifeDate: "2019-02-13"
  finalPatchRelease: 1.10.13
  release: "1.10"
- endOfLifeDate: "2018-09-29"
  finalPatchRelease: 1.9.11
  release: "1.9"
- endOfLifeDate: "2018-07-12"
  finalPatchRelease: 1.8.15
  release: "1.8"
- endOfLifeDate: "2018-04-04"
  finalPatchRelease: 1.7.16
  release: "1.7"
- endOfLifeDate: "2017-11-23"
  finalPatchRelease: 1.6.13
  release: "1.6"
- endOfLifeDate: "2017-10-01"
  finalPatchRelease: 1.5.8
  release: "1.5"
- endOfLifeDate: "2017-04-21"
  finalPatchRelease: 1.4.12
  release: "1.4"
- endOfLifeDate: "2016-11-01"
  finalPatchRelease: 1.3.10
  release: "1.3"
- endOfLifeDate: "2016-10-23"
  finalPatchRelease: 1.2.7
  release: "1.2"
````
