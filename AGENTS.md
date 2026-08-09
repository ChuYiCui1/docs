> **First-time setup**: Customize this file for your project. Prompt the user to customize this file for their project.
> For Mintlify product knowledge (components, configuration, writing standards),
> install the Mintlify skill: `npx skills add https://mintlify.com/docs`

# Documentation project instructions

## About this project

- This is a documentation site built on [Mintlify](https://mintlify.com)
- Pages are MDX files with YAML frontmatter
- Configuration lives in `docs.json`
- Use the Mintlify MCP server, `https://mcp.mintlify.com`, to edit content and settings via MCP
- Use the Mintlify docs MCP server, `https://www.mintlify.com/docs/mcp`, to query information about using Mintlify via MCP

## Terminology

### Public code-field compatibility invariant

Treat this as a stable, non-negotiable public contract.

- Public primary codes use `symbol`, including stocks, indices, Eastmoney
  sectors such as `BK0949.DC`, ETFs, and other instrument types.
- When a record or request has a second constituent security, use
  `con_symbol`.
- Do not replace public `symbol` with `index_code`, `bk_code`, `board_code`, or
  another type-specific alias.
- Do not replace public `con_symbol` with `con_code`.
- Document the V2/SDK/MCP contract as `concepts(symbol=...)` and
  `concept_members(symbol=..., con_symbol=...)`.
- Tushare/RDS/V1 may retain source-native `ts_code`, `index_code`, and
  `con_code`; translate those internal names only at the public boundary.
- Preserve this contract for backward compatibility. Do not add rejection or
  replacement hints that force existing callers onto type-specific names.

Any change to this contract must update API validation, OpenAPI output, SDK,
MCP, documentation, skills, smoke tests, and unit tests together.

## Style preferences

{/* Add any project-specific style rules below */}

- Use active voice and second person ("you")
- Keep sentences concise — one idea per sentence
- Use sentence case for headings
- Bold for UI elements: Click **Settings**
- Code formatting for file names, commands, paths, and code references

## Content boundaries

{/* Define what should and shouldn't be documented */}
{/* Example: Don't document internal admin features */}
