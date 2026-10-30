# Shamil Ichakaev

AI security engineer. I build testbeds to see which controls for LLM agents work in practice, for MCP servers, coding agents and information-flow policies. I also work in production infrastructure security (DLP, NGFW, PKI, SIEM), which is where I started.

## Projects

- [mcp-server-misbehaviour-matrix](https://github.com/shvma/mcp-server-misbehaviour-matrix) runs seven MCP server misbehaviours against six setups on a live testbed (agentgateway, OPA, Keycloak token exchange, PostgREST + RLS, a typed adapter). Each outcome is read from the target's state. Token exchange with per-user rights at the target blocks reads of other users' data, writes and token replay, with a median overhead of 0.25 ms on localhost, within run-to-run noise. No setup in the matrix stops a server from sending out data it received in the call.
- [claude-codex-baseline](https://github.com/shvma/claude-codex-baseline) is a 22-rule security baseline for Claude Code and OpenAI Codex. It comes with generated MDM profiles for Jamf and Intune, a checker that shows where the policy is not enforced, and a release gate that re-tests 8 of the rules on each new agent version.
- [coding-agent-sandbox-matrix](https://github.com/shvma/coding-agent-sandbox-matrix) compares Anthropic's sandbox-runtime with NVIDIA OpenShell for coding agents, using synthetic secrets and local receivers. It ends with a recommendation: a laptop pilot first, a separate environment for background agents and CI.
- [ifc-contract-linter](https://github.com/shvma/ifc-contract-linter) lints OpenAPPA tool contracts and reproduces a gap in the shipped Google Drive contract.

## Upstream

- [archestra-ai/OpenAPPA#747](https://github.com/archestra-ai/OpenAPPA/issues/747): I reported that the Google Drive contract lets internal data be written, copied or moved into an externally shared file or folder without review. A maintainer opened a fix in [#750](https://github.com/archestra-ai/OpenAPPA/pull/750). Reviewing the fix, I found two `update_file` flags it missed: one gives a folder its parent's readers, the other lets any editor reshare. The maintainer added checks for both and now refuses unknown arguments. Not merged yet.
- [NVIDIA/OpenShell#4035](https://github.com/NVIDIA/OpenShell/issues/4035): offline `openshell policy lint`. I asked to take it over with an implementation plan and am waiting for the issue to be accepted.

## Contact

[Telegram](https://t.me/shamqa)
