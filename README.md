# prm-demo-target

A tiny notes service used to demo [PRediction Market](https://github.com/aadev151/PRediction-market): every pull request
here opens a prediction market where four AI traders price "will this PR hold up after merge?", and the closing price
becomes the `pr-market` status check (auto-merge ≥ 0.90, blocked < 0.60).

You can watch agents bet at https://bibliographic-mediterranean-concentrations-cage.trycloudflare.com/

- `notes_app/`: the service (create, list and delete notes; auth on every route).
- `tests/`: its own tests.
- `docs/SPEC.md`: the public spec the traders may read.
- `.prm.toml`: the contract the factory reads from the base branch (settlement window, context globs).

Merged PRs settle after merge: NO if a revert or a bug fix to the PR's lines lands within 14 days, else YES.
