# Checkbox Assignment

A Playwright test that verifies checkbox interactions on
[The Internet checkbox page](https://the-internet.herokuapp.com/checkboxes).

## Prerequisites

- Node.js 20 or later and npm.
- Internet access to reach the test page and download dependencies and Chromium.

## Setup

From the project directory, install the locked dependencies and browser:

```sh
npm ci
npx playwright install chromium
```

## Run the test

```sh
npm test
```

Tests run headlessly using Chromium by default. To watch the browser:

```sh
npm test -- --headed
```

To generate and open an HTML report:

```sh
npm test -- --reporter=html
npx playwright show-report
```

## Test coverage

The test confirms that two checkboxes are visible, then verifies these states
in order:

1. Both checkboxes unchecked.
2. Only the first checkbox checked.
3. Both checkboxes checked.
4. Only the second checkbox checked.
5. Both checkboxes unchecked again.

The initial checkbox state is reset before these assertions.

## Project structure

```text
tests/checkboxes.spec.ts  Checkbox interaction test
playwright.config.ts     Test directory and headless configuration
package.json             Test command and Playwright dependency
package-lock.json        Locked dependency versions
```

Generated test artifacts are written to `test-results/`. HTML reports, when
requested, are written to `playwright-report/`.
