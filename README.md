# Guyana Revenue Authority Exchange Rates API — gracustoms-exchange-rate

[![npm version](https://img.shields.io/npm/v/gracustoms-exchange-rate.svg)](https://www.npmjs.com/package/gracustoms-exchange-rate)
[![license](https://img.shields.io/npm/l/gracustoms-exchange-rate.svg)](https://github.com/AllRates-Today/gracustoms-exchange-rate/blob/main/LICENSE)
[![zero dependencies](https://img.shields.io/badge/dependencies-0-brightgreen.svg)](https://www.npmjs.com/package/gracustoms-exchange-rate)
[![TypeScript](https://img.shields.io/badge/TypeScript-types%20included-3178C6.svg)](https://www.typescriptlang.org/)
[![USD/GYD today](https://img.shields.io/badge/dynamic/json?url=https%3A%2F%2Fallratestoday.com%2Fapi%2Fopen%2Fcentral-bank%2Fgracustoms%3Fsource%3DUSD%26target%3DGYD&query=%24.rate&label=USD%2FGYD%20official%2C%20Guyana%20Revenue%20Authority&color=0A7E8C&cacheSeconds=3600)](https://allratestoday.com/tax-authority-rates-api/gracustoms/)
[![rate date](https://img.shields.io/badge/dynamic/json?url=https%3A%2F%2Fallratestoday.com%2Fapi%2Fopen%2Fcentral-bank%2Fgracustoms%3Fsource%3DUSD%26target%3DGYD&query=%24.rate_date&label=rate%20date&color=555&cacheSeconds=3600)](https://allratestoday.com/tax-authority-rates-api/gracustoms/)

**Official Guyana Revenue Authority (Guyana) monthly exchange rates for Node.js and TypeScript. The published tax authority rates behind tax filings, customs valuations, audits, and compliant invoicing — not market estimates, but the numbers Guyana Revenue Authority itself prints, every month.**

## 🚀 Why this client?

- 🏛️ **Official rates** — Guyana Revenue Authority's own table, with the publisher's own `rate_date` on every response
- 📅 **History back to 2020** — point-in-time tables and daily series for any past date
- 🔀 **Official vs derived, always flagged** — computed inverse/cross pairs carry `derived: true`, never mixed with official prints
- ⚡ **Zero dependencies** — pure ESM + CJS over global `fetch`; Node 18+, Bun, Deno, and edge runtimes
- 🔷 **Type-safe** — full TypeScript definitions shipped with the package
- 🧾 **Compliance-grade metadata** — `rate_type`, publication date, and source disclaimer on every response

> **Official rate, not mid-market:** every value here is a number Guyana Revenue Authority itself published, fixed once printed and carrying the tax authority's own `rate_date` — what filings and audits require. Need the live mid-market rate for pricing or display instead? Use the [mid-market API](https://allratestoday.com/docs/) or [`@allratestoday/sdk`](https://www.npmjs.com/package/@allratestoday/sdk). The two can diverge by several percent.

## 🔑 Get your API key

Get a free API key at [allratestoday.com/register](https://allratestoday.com/register) — no credit card required. Latest rates are on every plan, including free.

## 📈 Latest official table

[![Latest Guyana Revenue Authority table](https://allratestoday.com/api/open/central-bank/gracustoms/table.svg)](https://allratestoday.com/tax-authority-rates-api/gracustoms/)

The image is rendered live from the keyless endpoint, so it follows the tax authority's publications on npm and on GitHub alike without a new release. The same table as text is folded below for search and copy-paste: on GitHub [a daily Action](.github/workflows/daily-table.yml) refreshes it whenever the tax authority publishes a new table; on npm it is as of the package's publish date.

<!-- daily-table:start -->
<details>
<summary>Table as text: published 2026-11-01 by Guyana Revenue Authority — 33 rates. Updated 2026-11-25.</summary>

| Base | Quote | Type | Rate |
| --- | --- | --- | ---: |
| AED | GYD | monthly | 56.77 |
| ARS | GYD | monthly | 0.14 |
| AUD | GYD | monthly | 146.68 |
| BBD | GYD | monthly | 104.25 |
| BRL | GYD | monthly | 38.42 |
| BSD | GYD | monthly | 208.5 |
| CAD | GYD | monthly | 149.37 |
| CHF | GYD | monthly | 253.34 |
| CNY | GYD | monthly | 31.33 |
| COP | GYD | monthly | 0.07 |
| DKK | GYD | monthly | 31.14 |
| EUR | GYD | monthly | 232.75 |
| GBP | GYD | monthly | 279.3 |
| HKD | GYD | monthly | 26.58 |
| INR | GYD | monthly | 2.2 |
| JMD | GYD | monthly | 1.31 |
| JPY | GYD | monthly | 1.32 |
| KRW | GYD | monthly | 0.16 |
| MXN | GYD | monthly | 11.09 |
| NGN | GYD | monthly | 0.15 |
| NOK | GYD | monthly | 22.65 |
| NZD | GYD | monthly | 117.48 |
| QAR | GYD | monthly | 55.56 |
| RUB | GYD | monthly | 2.59 |
| SEK | GYD | monthly | 21.21 |
| SGD | GYD | monthly | 163.18 |
| SRD | GYD | monthly | 5.55 |
| TTD | GYD | monthly | 31.07 |
| TWD | GYD | monthly | 6.4 |
| UAH | GYD | monthly | 4.67 |
| USD | GYD | monthly | 208.5 |
| XCD | GYD | monthly | 77.22 |
| ZAR | GYD | monthly | 12.48 |

</details>

Source: [Official rates published by GRACUSTOMS, served by AllRatesToday](https://allratestoday.com/tax-authority-rates-api/gracustoms/). Rates are as printed by the tax authority; AllRatesToday is not affiliated with it.
<!-- daily-table:end -->

## 📦 Installation

```bash
npm install gracustoms-exchange-rate
```

```bash
yarn add gracustoms-exchange-rate
```

```bash
pnpm add gracustoms-exchange-rate
```

Requires Node 18+ (global `fetch`); also runs on Bun, Deno and edge runtimes. Also published under the org scope as [`@allratestoday/gracustoms-exchange-rate`](https://www.npmjs.com/package/@allratestoday/gracustoms-exchange-rate) — same code, same versions.

## 🏁 Quick start

```js
import { getRate } from 'gracustoms-exchange-rate';

const pair = await getRate('USD', 'GYD', { apiKey: 'art_live_...' });
console.log(pair.rate, pair.rate_date); // the official Guyana Revenue Authority rate, on the tax authority's own date
```

## 📚 API reference

- [Latest pair rate](#latest-pair-rate) — one pair from the latest official table
- [Full official table](#full-official-table) — everything the tax authority printed, in one call
- [Table for a date](#table-for-a-date) — the official table for an invoice or filing date
- [Daily time series](#daily-time-series) — one pair across a date range

---

### Latest pair rate

Free plan and up. Pairs the tax authority does not print directly are resolved from its table and flagged (see *Official vs derived rates* below).

```js
const pair = await getRate('USD', 'GYD', { apiKey: 'art_live_...' });
```

**Response:**

```javascript
{
  bank: 'gracustoms',
  name: 'Guyana Revenue Authority',
  rate_date: '2026-11-01',   // Guyana Revenue Authority's own publication date
  source: 'USD',
  target: 'GYD',
  rate: 208.5,
  rate_type: 'monthly',
  derived: false,
  method: 'published',
  disclaimer: 'Official rates as published by the named central bank. On weekends/holidays the most recent published rate_date is returned.'
}
```

### Full official table

Free plan and up. The complete table for the latest publication date.

```js
import { getLatestRates } from 'gracustoms-exchange-rate';

const table = await getLatestRates({ apiKey: 'art_live_...' });
console.log(table.rate_date, table.rates.length);
```

**Response:**

```javascript
{
  bank: 'gracustoms',
  name: 'Guyana Revenue Authority',
  rate_date: '2026-11-01',
  rates: [
    { "base": "USD", "quote": "GYD", "type": "monthly", "value": 208.5 },
    // … the rest of the official table (34 currencies vs GYD)
  ],
  disclaimer: '…'
}
```

### Table for a date

Paid plans. The official table for any date since 2020 — weekends and holidays return the most recent published date, flagged via `published_on_requested_date`, which is exactly the in-force rate a filing needs.

```js
import { getRatesForDate } from 'gracustoms-exchange-rate';

const day = await getRatesForDate('2026-06-30', { apiKey: 'art_live_...' });
// Optionally narrow to one pair:
const one = await getRatesForDate('2026-06-30', { apiKey: 'art_live_...', source: 'USD', target: 'GYD' });
```

**Response:**

```javascript
{
  bank: 'gracustoms',
  requested_date: '2026-06-30',
  rate_date: '2026-06-30',                // the date actually published
  published_on_requested_date: true,      // false when a weekend/holiday fell back
  rates: [ /* the full table for that date */ ],
  disclaimer: '…'
}
```

### Daily time series

Paid plans. One resolved rate per publication date — ready for charting, revaluation runs, or audit workpapers.

```js
import { getHistory } from 'gracustoms-exchange-rate';

const series = await getHistory(
  { source: 'USD', target: 'GYD', from: '2026-01-01', to: '2026-11-01' },
  { apiKey: 'art_live_...' }
);
```

**Response:**

```javascript
{
  bank: 'gracustoms',
  source: 'USD',
  target: 'GYD',
  from: '2026-01-01',
  to: '2026-11-01',
  count: 152,
  rates: [
    // one entry per publication date
    { date: '2026-11-01', rate: 208.5, rate_type: 'monthly', derived: false, method: 'published' },
    // …
  ],
  disclaimer: '…'
}
```

Pass `{ symbol: 'USD' }` instead of `source`/`target` to get the raw published rows for one currency (all rate types, no pair resolution).

---

## 🗺️ Currencies covered

Guyana Revenue Authority currently publishes rates covering **34 currencies** against the GYD (as of the latest table):

🇦🇪 `AED` · 🇦🇷 `ARS` · 🇦🇺 `AUD` · 🇧🇧 `BBD` · 🇧🇷 `BRL` · 🇧🇸 `BSD` · 🇧🇾 `BYN` · 🇨🇦 `CAD` · 🇨🇭 `CHF` · 🇨🇳 `CNY` · 🇨🇴 `COP` · 🇩🇰 `DKK` · 🇪🇺 `EUR` · 🇬🇧 `GBP` · 🇭🇰 `HKD` · 🇮🇳 `INR` · 🇯🇲 `JMD` · 🇯🇵 `JPY` · 🇰🇷 `KRW` · 🇲🇽 `MXN` · 🇳🇬 `NGN` · 🇳🇴 `NOK` · 🇳🇿 `NZD` · 🇶🇦 `QAR` · 🇷🇺 `RUB` · 🇸🇪 `SEK` · 🇸🇬 `SGD` · 🇸🇷 `SRD` · 🇹🇹 `TTD` · 🇹🇼 `TWD` · 🇺🇦 `UAH` · 🇺🇸 `USD` · `XCD` · 🇿🇦 `ZAR`

## 🏛️ Source

The monthly rates of exchange the Guyana Revenue Authority fixes under the proviso to section 22(1)(a) of the Customs Act, Chapter 82:01, in Guyana dollars per unit of foreign currency. They are the rates used to convert foreign-currency values into Guyana dollars when customs duty is assessed during the month.

- Publisher's own page: [Monthly customs rates of exchange](https://gra.gov.gy/exchange-rates/) · [gra.gov.gy](https://gra.gov.gy/)
- Publication: every month; the exact schedule, freshness status and any current delay are on the [Guyana Revenue Authority rates page](https://allratestoday.com/tax-authority-rates-api/gracustoms/)
- Values are stored unmodified, with the publisher's own `rate_date` on every row — see the [methodology](https://allratestoday.com/official-rates-methodology/)

## 🧭 Reading the numbers

- `value` is always **quote currency per 1 unit of base currency** (`base: "EUR", quote: "USD", value: 1.15` means 1 EUR = 1.15 USD).
- Guyana Revenue Authority quotes **GYD per 1 unit of foreign currency** (e.g. `base: "USD", quote: "GYD"` means GYD per one US dollar).
- Need the other way round? Ask `getRate(target, source)` and the API inverts or crosses for you, flagged `derived: true` — never divide a published rate yourself in a compliance workflow.
- `rate_type` tells you which of the tax authority's series a row belongs to (`monthly` here); some publishers print buy/sell or several fixings for the same pair.

## 🧩 ERP & accounting systems

Loading the official Guyana Revenue Authority rate into an accounting system is a supported workflow, not a hack. Step-by-step guides with the direction each system expects:

- [Dynamics 365 Business Central](https://allratestoday.com/docs/integrations/business-central/) — built-in Currency Exchange Rate Service, no code
- [Xero](https://allratestoday.com/docs/integrations/xero/) · [QuickBooks Online](https://allratestoday.com/docs/integrations/quickbooks/) · [SAP S/4HANA and ECC](https://allratestoday.com/docs/integrations/sap/) · [Odoo](https://allratestoday.com/docs/integrations/odoo/)

The same keyed endpoints return `?format=csv`, `?format=xml` and `?format=xlsx`, and accept the key as `?api_key=` on the URL for importers that cannot send headers:

```bash
curl "https://allratestoday.com/api/v1/central-bank/gracustoms/latest?format=xml&api_key=art_live_..."
```

## 🤖 AI agents

- MCP server: `npx -y @allratestoday/central-bank-mcp` (stdio) or the hosted endpoint `https://allratestoday.com/api/mcp` — tools for official rates, history, cross-bank comparison and publication calendars
- Already using the general SDK or MCP server? Since 2026-10-01 [`@allratestoday/sdk`](https://www.npmjs.com/package/@allratestoday/sdk) 1.4+ has `officialRates('gracustoms')` and [`@allratestoday/mcp-server`](https://www.npmjs.com/package/@allratestoday/mcp-server) 0.6+ has a `get_official_rates` tool — both return this source's latest table with no key, so you can add it without a second dependency
- Claude Code plugin (no key): `/plugin marketplace add AllRates-Today/claude-code-plugin` then `/plugin install allratestoday@allratestoday` — bundles both MCP servers plus an `/official-rate gracustoms ...` command
- Evaluating? Agents can self-issue a trial key with no signup: `POST https://allratestoday.com/api/agent/keys` (send `Content-Type: application/json`) returns a 100-call key valid 7 days that covers the free-plan methods (latest table, pairs); dated tables and history need a [paid plan](https://allratestoday.com/pricing/). The MCP servers expose it as `request_trial_key`
- Machine-readable site guide: [llms.txt](https://allratestoday.com/llms.txt) · [for-ai-agents](https://allratestoday.com/for-ai-agents/)

## ⚖️ Official vs derived rates

If Guyana Revenue Authority does not print a pair directly, the API resolves it from the tax authority's own table and says so — official and computed values are never confused:

| `method` | `derived` | Meaning |
| --- | --- | --- |
| `published` | `false` | The tax authority printed this pair directly |
| `inverse` | `true` | Computed as 1 ÷ the published opposite direction |
| `cross` | `true` | Computed via GYD from two published rates |

## 🛡️ Error handling

Errors are thrown as `Error` with `status` (HTTP code) and `body` (the API's JSON error) attached:

```js
try {
  const pair = await getRate('USD', 'XXX', { apiKey: 'art_live_...' });
} catch (err) {
  console.log(err.message); // human-readable reason
  console.log(err.status);  // e.g. 404
}
```

| Status | Meaning |
| ------ | ------- |
| — | Missing `apiKey` (thrown before any request) |
| `400` | Malformed date or parameters |
| `401` | Invalid API key |
| `403` | Endpoint needs a [paid plan](https://allratestoday.com/pricing/) (historical dates & series) |
| `404` | Pair or date range not covered by Guyana Revenue Authority |
| `429` | Monthly quota exceeded |

## 🔷 TypeScript

Full definitions ship with the package — no `@types` install:

```ts
import type { LatestRates, PairRate, DatedRates, RateEntry, HistoryQuery, RequestOptions } from 'gracustoms-exchange-rate';
```

## 📦 CommonJS

```javascript
const { getRate } = require('gracustoms-exchange-rate');

getRate('USD', 'GYD', { apiKey: 'art_live_...' }).then((pair) => console.log(pair.rate));
```

## 💡 Quota tips

- Rates change once a month — cache the official table locally and a small monthly quota goes a long way.
- Every request counts toward your AllRatesToday quota, shared across all AllRatesToday endpoints on your key.

## 📖 Methods reference

| Method | Plan | Description |
| ------ | ---- | ----------- |
| `getRate(source, target, { apiKey })` | Free | Latest rate for one pair, resolved from the official table |
| `getLatestRates({ apiKey })` | Free | The tax authority's full latest official table |
| `getRatesForDate(date, { apiKey, source?, target? })` | Paid | The official table (or one pair) for a YYYY-MM-DD date |
| `getHistory({ symbol \| source+target, from?, to? }, { apiKey })` | Paid | Daily series since 2020 |

## 📥 Bulk data (no key)

Need the whole archive rather than an API call? The same official tables are mirrored daily as open data:

- Hugging Face: [AllRatesToday/central-bank-exchange-rates](https://huggingface.co/datasets/AllRatesToday/central-bank-exchange-rates) — one CSV per institution (`rates/gracustoms.csv`)
- Kaggle: [allratestoday/central-bank-exchange-rates](https://www.kaggle.com/datasets/allratestoday/central-bank-exchange-rates)
- Raw JSON on GitHub: `https://raw.githubusercontent.com/AllRates-Today/central-bank-exchange-rates/main/data/gracustoms/latest.json`

## 🔗 Links

- **Website:** [allratestoday.com](https://allratestoday.com)
- [Guyana Revenue Authority rates page](https://allratestoday.com/tax-authority-rates-api/gracustoms/) — live table, publication cadence, FAQ
- [All tax authority sources](https://allratestoday.com/tax-authority-rates-api/) · [Full list of 120+ central banks and 50+ tax authorities](https://allratestoday.com/central-bank-rates-api/institutions/) — one API, the same response shape for every source
- [Download central bank rates](https://allratestoday.com/download-central-bank-rates/) — every bank's latest table and history as Excel, CSV or JSON
- [Bank Exchange Rate API](https://allratestoday.com/bank-exchange-rate-api/) — live buy and sell rates from 1,200+ commercial banks in 120+ countries · [npm](https://www.npmjs.com/package/bank-exchange-rates) · [GitHub](https://github.com/AllRates-Today/bank-exchange-rates)
- [Package docs on the site](https://allratestoday.com/docs/sdk/gracustoms-exchange-rate/) · [ERP integration guides](https://allratestoday.com/docs/integrations/)
- [API documentation](https://allratestoday.com/docs/#central-bank) · [Interactive reference](https://allratestoday.com/api-reference/) · [Methodology](https://allratestoday.com/official-rates-methodology/)
- [Register (Free)](https://allratestoday.com/register) · [Dashboard](https://allratestoday.com/profile) · [Pricing](https://allratestoday.com/pricing/)
- [Status](https://allratestoday.com/status)
- [Postman collection](https://allratestoday.com/postman/)
- [ChatGPT app](https://chatgpt.com/plugins/plugin_asdk_app_6ae1e76098f48191a285ac3f5ab7a83b) — ask ChatGPT for live and official central bank rates
- [OpenAPI reference on Bump.sh](https://bump.sh/allratestoday/doc/allratestoday-api) — also on [SwaggerHub](https://app.swaggerhub.com/apis-docs/allratestoday/allratestoday-exchange-rate-central-bank-rates-api/2.2.0)
- [GitHub](https://github.com/AllRates-Today/gracustoms-exchange-rate)

## 📜 License

MIT
