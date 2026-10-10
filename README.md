<p align="center"><img src="assets/logo.png" alt="OQRO" width="96"></p>

# OQRO MCP server

Ask Claude, ChatGPT, Cursor or any MCP client about **insider trades, Congress stock trades, hedge fund 13F moves and federal contracts** for US-listed companies. Every answer comes with the official filing it was read from.

- **Server (remote, Streamable HTTP):** `https://oqro.io/api/mcp`
- **Website and setup page:** <https://oqro.io/mcp>
- **Protocol:** MCP `2025-06-18`
- **Auth:** OAuth 2.1 with PKCE and dynamic client registration (sign in with an OQRO account). The tool list is open; every tool call is checked against an active OQRO Pro subscription ($9.99 a month or $79.99 a year).

OQRO describes what was filed. It is not investment advice.

## Connect

**Claude Code**

```bash
claude mcp add --transport http oqro https://oqro.io/api/mcp
```

**Cursor** (`~/.cursor/mcp.json`)

```json
{ "mcpServers": { "oqro": { "url": "https://oqro.io/api/mcp" } } }
```

**Claude, ChatGPT and other clients:** add a remote MCP server (custom connector) with the URL above, then sign in when asked. Step-by-step screens are on <https://oqro.io/mcp>.

## Tools (15)

| Tool | What it does |
|---|---|
| `search_companies` | Find a covered company by ticker or name. |
| `get_company` | Profile, latest close against the S&P 500, revenue and net income from SEC filings, counts of recent disclosures. |
| `latest_results` | Latest quarter, trailing twelve months, fiscal year and balance sheet from the company's own SEC filings. |
| `pre_mortem` | Measurable facts for a risk review: cash burn, debt, profit trend, dilution, insider buying and red-flag filings. |
| `insider_trades` | Officer, director and 10% owner trades from SEC Form 4, plus Form 144 notices of planned sales. |
| `rare_insider_trades` | Insider trades that stand out against the company's own record since 2006, each with plain-sentence signals. |
| `insider_record` | Open-market purchases and sales per year since 2006 for one company or one person. |
| `congress_trades` | Stock transactions disclosed by members of Congress (House Clerk and Senate), with the official amount ranges. |
| `fund_moves` | Position changes in SEC Form 13F of the managers OQRO follows. |
| `convergence` | Companies where insiders, funds and Congress lean the same way at the same time. |
| `federal_contracts` | Prime federal contract awards mapped to public companies (USAspending.gov). |
| `lobbying` | Federal lobbying spend per quarter from Lobbying Disclosure Act reports. |
| `price_history` | Daily, weekly or monthly closes next to the S&P 500, with drawdown from the high. |
| `screen` | Filter and sort about 850 covered companies on published numbers. |
| `leaderboard` | Members of Congress or insiders ranked by how their disclosed purchases did against the S&P 500. |

## Example questions

- Which insiders bought their own company's stock on the open market in the last 30 days, and which purchases were the largest?
- Which insider purchases this week stand out against that company's last 20 years of filings?
- Show the politician trades in NVDA over the last year, with the official amount range and the link to each filing.
- What did Berkshire Hathaway add to, trim or exit in its latest 13F?
- Run a pre-mortem on Boeing: free cash flow, debt, dilution and the red-flag filings of the last 12 months.

## Sources

SEC EDGAR (Forms 4, 5, 144, 13F, 8-K, Schedules 13D and 13G), House and Senate periodic transaction reports, USAspending.gov, Lobbying Disclosure Act reports. Every record links to its source document.

## Free pages (no account)

- Rare insider trades, this week: <https://oqro.io/rare-insider-trades>
- Weekly recap of insider and Congress trades: <https://oqro.io/weekly>

## Limits

Filings can arrive late (the trade date can be weeks before the filing date; both are shown). Senate paper filings are read by OCR and can be incomplete. Coverage and freshness per source are on <https://oqro.io/status>.

## License

The files in this repository are MIT licensed. The OQRO service and its data are covered by <https://oqro.io/terms>.
