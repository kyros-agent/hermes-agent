# Kyros Experimental Release — Browser Backend Hygiene

**Date:** April 9, 2026
**Base:** `origin/main` (official upstream)
**Branch:** `kyros/browser-backend-hygiene`

This private experimental release hardens Hermes browser configuration and diagnostics without changing the official upstream tracking model.

## What changed

- Added config validation that warns when browser automation MCP servers are registered in `mcp_servers`
- Added doctor checks for the active Camofox backend and profile-scoped persistence
- Added tests covering the browser MCP hygiene and doctor behavior
- Removed an incorrect root-vs-profile drift check that produced false positives

## Verification

- `pytest -q tests/hermes_cli/test_config_validation.py tests/hermes_cli/test_doctor.py`
- `hermes doctor`
- `hermes config check`

## Tracking model

- Pull / sync path stays on the official upstream: `origin/main`
- Push path for private work stays on `kyros`
- Safety backup branch preserved: `backup/pre-heart-20260409-060643`

## Notes

This is an experimental private release note, not an upstream release artifact.
It documents the operator-intended path while keeping the repo aligned to the official source of truth.
