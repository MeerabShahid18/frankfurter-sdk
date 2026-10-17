# Frankfurter TypeScript SDK

An unofficial TypeScript SDK for the [Frankfurter API](https://frankfurter.dev/), generated using [Voxgig SDKGen](https://github.com/voxgig/sdkgen).

Frankfurter provides foreign exchange rates and related data. This project generates a structured TypeScript client from the API's OpenAPI specification.

This SDK is an independent community project and is not affiliated with or endorsed by the Frankfurter API maintainers.

## Features

- Generated TypeScript client based on an OpenAPI specification.
- Entity-based API for currencies, rates, providers, and coverage.
- Built-in test mode for offline testing.
- TypeScript build and automated test suite.

## Quick start

From the repository root, run:

```bash
cd ts
npm install
npm run build
```

## Run tests

```bash
npm test
```

The previous test run reported 237 passing tests, 0 failures, and 12 skipped tests.

## Example: Fetch an exchange rate

Run this example from the `ts` directory after building the project:

```javascript
const { FrankfurterSDK } = require('./dist/FrankfurterSDK.js');

async function main() {
  const client = new FrankfurterSDK();

  const result = await client.Rate().load({
    base: 'USD',
    quote: 'EUR',
  });

  console.log(result.data());
}

main().catch(console.error);
```

## Generated entities

- **Coverage** — API coverage information.
- **Currency** — currency-related data.
- **Provider** — provider information.
- **Rate** — exchange-rate data.

## Project structure

- `.sdk/` — SDKGen project files and OpenAPI definition.
- `ts/` — generated TypeScript SDK, tests, and language-specific documentation.
- `LICENSE` — license terms.

## Resources

- [Frankfurter API](https://frankfurter.dev/)
- [Voxgig SDKGen](https://github.com/voxgig/sdkgen)

## Validation

The TypeScript project built successfully, its automated tests completed, and a live USD-to-EUR request through the generated SDK was verified.

## License

See the included `LICENSE` file for the applicable license terms.