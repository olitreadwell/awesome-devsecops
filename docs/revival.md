# What this revival changed

`jakob-pennington/awesome-devsecops` last took a push in August 2024. This fork
runs the list on the gate from
<https://github.com/olitreadwell/awesome-list-template>, pinned to engine
revision `0d13482`.

## The readme

- The page opened with a banner image, a centred badge, and a rule, with no
  level one heading anywhere. It has `# Awesome DevSecOps` with the standard
  Awesome badge now. The banner image upstream drew stays where it was, and the
  centred badge block came out, because the linter reads a centred image as a
  heading.
- The file is `readme.md`, upstream's spelling, and `awesome.toml` points at
  that name rather than `README.md`. Nothing was renamed.

## Entries

- Nineteen entries carried an author in italics that repeated the item name, as
  in `- [Cybrary](https://www.cybrary.it/) - _Cybrary_ - Subscription based
  online courses...`. The linter refuses a description that opens with the item
  name, so the repeated author came out and the rest of the text is untouched.
  The same repair hit `Gauntlt`, `Hadolint`, `Gopass`, `Selefra`, `SpotBugs`,
  and fourteen others.
- Four URLs were listed twice. The later copy came out in each pair: `DevSecCon`
  under Conferences (the Communities entry above it stayed), `git-secrets` under
  Secrets Scanning, `Awesome Threat Modelling` and `Vulnerable Web Apps
  Directory` under Related Lists.
- `Juice Shop` pointed at `github.com/bkimminich/juice-shop`, which 404s. The
  project lives at `github.com/juice-shop/juice-shop` now, and the entry uses
  that URL. Star count and last push came from `make stats` afterwards.
- Three entries had trailing whitespace at the end of the line, and four opened
  the entry text with a lowercase letter: the author fields `_terraform-compliance_`,
  `_r2c_`, and `_securego_` are capitalised, and the `Sigstore`
  entry no longer opens by repeating its own name.
- `Auth0/repo-supervisor` is gone from GitHub, so `Repo-supervisor` cannot carry
  a star count. The URL sits in `links.allowlist` with that reason. A maintainer
  should decide whether the entry points somewhere else or comes out.

## Left alone

- Every description in the list is the words upstream wrote. This pass changed
  separators, punctuation, capitalisation of a first word, and link targets,
  nothing more.
- No entry is missing a description, so `tests/test_readme.py` holds a count of
  zero and a floor of 151 entries, and neither may drift.
- The spell warnings stay. `kubernetes`, `git`, and `terraform` are lowercase
  inside entry text, which is how those entries were written.

## Tooling

- `pyproject.toml` pins the engine, `Makefile` carries the engine targets, and
  `AGENTS.md` describes the layout.
- `github-stats.json` records stars and last push for the 71 GitHub entries
  that resolve, and `exports/` holds the list as JSON, NDJSON, and CSV.
- `.githooks/pre-commit` and `.githooks/pre-push` run the gate. Install them
  with `make hooks-install`.
- `make check` covers the list rules, the Contents block, the stats snapshot,
  the exports, and the tests.
