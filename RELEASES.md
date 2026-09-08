# gaurs-infrastructure fork — Open WebUI releases

This repo is a public fork of [open-webui/open-webui](https://github.com/open-webui/open-webui),
maintained for [gaurs-infrastructure](https://github.com/gaurmudit/gaurs-infrastructure)
issue #146 (per-conversation `x-opencode-session` header on outbound opencode.ai
calls).

## Tag scheme

`v<upstream_version>-oc.<N>` — `N` is monotonic across all fork releases:

- `v0.11.3-oc.1` — first release (baseline upstream `v0.11.3` + the single header patch).
- Every new fork release (upstream rebase or our own fix) bumps `N`
  (`-oc.2`, `-oc.3`, …).
- Rare feature-bearing releases use `v<upstream>-oc.<N>.<M>`.

## Releases

| Fork tag | Upstream baseline | Patch contents |
|---|---|---|
| `v0.11.3-oc.1` | upstream `v0.11.3` (`2a960a59fe1dbbd35282f0556b3666d81102e781`) | `backend/open_webui/routers/openai.py` — URL-scoped `x-opencode-session` + `gaurs-ow/<BUILD_HASH>` User-Agent injection in `get_headers_and_cookies()` (commit `8bafc6172`). Docker build/publish workflow in `.github/workflows/docker.yml` (commit `3f5f4a7a8`). |
