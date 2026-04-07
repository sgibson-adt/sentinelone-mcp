# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/).

## [Unreleased]

### Added
- Initial release: multitenant Streamable HTTP wrapper around `sentinel-one/purple-mcp`.
- Fastify proxy on `:8080` exposing `POST /mcp` and `GET /health`.
- Per-tenant lazy spawning of `purple-mcp --mode streamable-http` children, keyed by `(token, base-url)` hash, with idle eviction.
- Header-based credential injection (`x-purplemcp-token`, `x-purplemcp-base-url`).
- Multi-stage Dockerfile bundling `uv`-installed `purple-mcp` plus the Node proxy.
- GitHub Actions workflow that builds and publishes the image to `ghcr.io/wyre-technology/sentinelone-mcp`.
