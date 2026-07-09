# Mock Premium Calculation API

A free, static mock API hosted on GitHub Pages. Each endpoint returns a fixed,
predefined JSON response with `Content-Type: application/json` and permissive CORS.

> **GET only.** These are static files — request bodies, query params, and methods
> other than GET are ignored. The response is always the same.

## Endpoints

Base path: `internal-premium-calculation/`

| Endpoint | Response shape |
| --- | --- |
| `regularMotor.json` | `basicExcess` + `annualRiskPremium` + `sumInsured` |
| `buildingRisk.json` | `excess` + `dolomiteMessage` |
| `specifiedallrisk.json` | `excess` + premiums |
| `liability.json` | `excess` + premiums |
| `caravan.json` | `excess` + premiums |
| `trailer.json` | `excess` + premiums |
| `motorcycle.json` | `excess` + premiums |
| `watercraft.json` | `excess` + premiums |
| `houseContentsRisk.json` | `excess` + premiums |
| `unspecifiedAllRisk.json` | `excess` + premiums |
| `classicmotor.json` | `excess` + premiums |

## Data Sync endpoints

| Endpoint | Response shape |
| --- | --- |
| `data-sync/api/v1/db/explore/Product` | table metadata: `columns`, `children`, `rowCount`, `columnCount` |

> This endpoint is an extensionless file so the URL matches the real API path.
> GitHub Pages serves it without a JSON content type; `fetch(...).json()` still
> works. If your client requires `Content-Type: application/json`, use the
> `Product.json` twin at the same path.

## Usage

```js
const res = await fetch("https://<user>.github.io/<repo>/internal-premium-calculation/regularMotor.json");
const data = await res.json();
```

Open `index.html` (the Pages site root) for a clickable list of all endpoints.
