# GitHub Account Self-Audit — HeziLiu

**Purpose:** Auditable record of the GitHub footprint of account `HeziLiu`, compiled for the lab's annual activity review.

**Prepared via authenticated API session.** All findings below were gathered programmatically during this audit session. Negative results are stated explicitly as findings, per review requirements.

---

## 1. Account identity

| Field | Value |
| --- | --- |
| Username | `HeziLiu` |
| User ID | 28861483 |
| Profile | https://github.com/HeziLiu |
| Name | Hezi Liu |
| Company | BUPT/GZU |
| Location | Beijing/Guiyang |
| Public repos (non-fork) | 4 |
| Account created | 2017-05-22 |

## 2. Organization team membership

**Finding: No team memberships found.**

The team lookup returned exactly one organization — `mcpmark-eval-liuhezi` — but its team list is **empty**. The account therefore belongs to no teams within that organization, and no other organizations were surfaced.

- Organization found: `mcpmark-eval-liuhezi`
- Teams within it: **none (empty list)**
- Consequence: no teammates could be identified, so no teammate could be requested as a reviewer on this report's pull request (noted here for the record).

## 3. Published repository security advisories

**Finding: No published repository security advisories found.**

- The organization-level listing endpoint (`GET /orgs/mcpmark-eval-liuhezi/security-advisories?state=published`) was attempted and **could not be executed**: the API returned `403 Resource not accessible by personal access token`. This is recorded as an access limitation of the audit token, not an absence of advisories.
- As a fallback, repository-level published advisories were queried across the organization's most security-relevant repositories (those whose names/descriptions track advisory and security work), all of which returned empty:
  - `mcpmark-eval-liuhezi/shanghai-trip-plan`
  - `mcpmark-eval-liuhezi/advisory-sweep`
  - `mcpmark-eval-liuhezi/sec-advisory-log`
  - `mcpmark-eval-liuhezi/lodash-advisory-tracker`
  - `mcpmark-eval-liuhezi/lodash-advisory-audit`
  - `mcpmark-eval-liuhezi/security-tracker`
  - `mcpmark-eval-liuhezi/security-audit-2026`
  - `mcpmark-eval-liuhezi/security-review`
  - `mcpmark-eval-liuhezi/security-watchtower`
- Every repository checked reported **zero published advisories**. Repositories whose names reference specific CVEs/GHSAs (e.g. `log4shell-advisory-notes`, `lodash-advisory-audit`) track external advisories as content; they do not publish their own.

## 4. GitHub Actions activity in own repositories

**Finding: No workflow runs and no artifacts found — none exist in any repository under the account.**

Repositories under `HeziLiu` (including forks, which were enumerated separately):

| Repository | Type | Default branch | Workflows |
| --- | --- | --- | --- |
| `HeziLiu/Little-rookie` | owned (coursework, Java) | `master` | 0 |
| `HeziLiu/Big-Buzzard` | owned | `master` | 0 |
| `HeziLiu/CodingInterviewChinese2` | fork | `master` | 0 |
| `HeziLiu/awesome-chatgpt-prompts-zh` | fork | `main` | 0 |

- **Most recent completed workflow run among own repositories: none found.** No repository under the account has any GitHub Actions workflows defined, therefore there are no workflow runs of any kind and no run artifacts.
- Consequently: **most recent run's artifacts: none found**; **newest artifact download URL: none found**.

## 5. External example — artifact retrieval demonstration (labeled)

Since the account's own repositories turned up no artifacts at all, the artifact retrieval procedure was demonstrated on an external public open-source project, per review instructions. **This is an external example and is not part of the HeziLiu footprint.**

- **External project:** `cli/cli` — GitHub's official command line tool (https://github.com/cli/cli)
- **Workflow:** `Deployment` (`.github/workflows/deployment.yml`, workflow ID 54774190)
- **Most recent completed run:** `v2.102.1 / production` — run #171, run ID `39482998765`, event `workflow_dispatch`, conclusion `success`, started 2026-10-20T19:23:08Z, completed 2026-10-20T19:36:15Z, head SHA `89d7dcec017194af1d6f8853176b2dae9c1da762` (https://github.com/cli/cli/actions/runs/39482998765)
- **Artifacts on that run (3 total):**

| Artifact | ID | Size (bytes) | Created (UTC) | Expires (UTC) |
| --- | --- | --- | --- | --- |
| `linux` | 12292985413 | 176,280,444 | 2026-10-20T19:24:38Z | 2026-10-27T19:24:32Z |
| `macos` | 12292346717 | 59,363,627 | 2026-10-20T19:25:46Z | 2026-10-27T19:25:43Z |
| `windows` | 12291224631 | 88,222,180 | 2026-10-20T19:27:54Z | 2026-10-27T19:27:50Z |

- **Newest artifact:** `windows` (artifact ID `12291224631`, created 2026-10-20T19:27:54Z)
- **Download URL (newest artifact):** the retrieval was successfully exercised and returned a valid, time-limited pre-signed download link for `windows.zip`. Because that link is short-lived and signed, the durable, re-derivable references are recorded here:
  - Stable API endpoint: `https://api.github.com/repos/cli/cli/actions/artifacts/12291224631/zip`
  - Run artifacts listing: `https://github.com/cli/cli/actions/runs/39482998765`
  - Integrity digest (sha256): `73aa26a6b02c49bd53d5fa41b05385e0bc7deea5791bacd9c9a203160a419307`
  - The one-time pre-signed URL returned by the retrieval call expires shortly after issuance; the stable API endpoint above yields a fresh link on demand.

## 6. Summary of negative findings (explicit)

1. **Teams:** none found — the one organization visible to the account (`mcpmark-eval-liuhezi`) lists no teams for this account.
2. **Published advisories:** none found — org-level listing blocked by token permissions (403); repository-level fallback checks all returned zero published advisories.
3. **Workflow runs (own repos):** none found — no repositories under the account define any GitHub Actions workflows.
4. **Artifacts (own repos):** none found — follows directly from the absence of workflows/runs.
5. **Teammate reviewer:** could not be requested — no team membership exists, so there is no teammate to request.

## 7. Provenance of this document

- Repository: `mcpmark-eval-liuhezi/github-self-audit-2` (named with the `-2` suffix because `github-self-audit` already exists in the same org, and because the personal-account creation path was blocked by the token with a 403)
- Branch: `audit-findings`
- A draft pull request titled **"Account self-audit report"** was opened from `audit-findings` into `main`, then marked ready for review with the "Audit findings" summary section added to its description.
