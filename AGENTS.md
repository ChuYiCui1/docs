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

### Eastmoney sector code naming invariant

Treat this as a stable, non-negotiable public contract.

- An Eastmoney sector code such as `BK0949.DC` is always named `bk_code`.
- Never accept or return a `BKxxxx.DC` value under `symbol`.
- In Eastmoney sector-constituent APIs, keep the constituent stock field named
  `con_code`, such as `000001.SZ`; do not rename it to `symbol` or
  `con_symbol`.
- Do not introduce `board_code` or `sector_code` as aliases for `bk_code`.
- Document the V2/SDK/MCP contract as `concepts(bk_code=...)` and
  `concept_members(bk_code=..., con_code=...)`.
- Tushare/RDS/V1 retain source-native `ts_code` and `con_code`. At the public
  boundary, translate only sector `ts_code` to `bk_code`; keep `con_code`
  unchanged.
- `con_symbol` may remain in unrelated index/ETF constituent contracts, but
  must not be used for Eastmoney sector constituents.

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
