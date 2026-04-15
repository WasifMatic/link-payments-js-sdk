
# Getting Started with APIMATIC Calculator

## Introduction

Simple calculator API hosted on APIMATIC

## Install the Package

Run the following command from your project directory to install the package from npm:

```bash
npm install link-payments-sdk@2.2.0
```

For additional package details, see the [Npm page for the link-payments-sdk@2.2.0 npm](https://www.npmjs.com/package/link-payments-sdk/v/2.2.0).

## Initialize the API Client

**_Note:_** Documentation for the client can be found [here.](https://www.github.com/WasifMatic/link-payments-js-sdk/tree/2.2.0/doc/client.md)

The following parameters are configurable for the API Client:

| Parameter | Type | Description |
|  --- | --- | --- |
| timeout | `number` | Timeout for API calls.<br>*Default*: `30000` |
| httpClientOptions | [`Partial<HttpClientOptions>`](https://www.github.com/WasifMatic/link-payments-js-sdk/tree/2.2.0/doc/http-client-options.md) | Stable configurable http client options. |
| unstableHttpClientOptions | `any` | Unstable configurable http client options. |
| logging | [`PartialLoggingOptions`](https://www.github.com/WasifMatic/link-payments-js-sdk/tree/2.2.0/doc/partial-logging-options.md) | Logging Configuration to enable logging |

The API client can be initialized as follows:

### Code-Based Client Initialization

```ts
import { Client, LogLevel } from 'link-payments-sdk';

const client = new Client({
  timeout: 30000,
  logging: {
    logLevel: LogLevel.Info,
    logRequest: {
      logBody: true
    },
    logResponse: {
      logHeaders: true
    }
  },
});
```

### Configuration-Based Client Initialization

```ts
import * as path from 'path';
import * as fs from 'fs';
import { Client } from 'link-payments-sdk';

// Provide absolute path for the configuration file
const absolutePath = path.resolve('./config.json');

// Read the configuration file content
const fileContent = fs.readFileSync(absolutePath, 'utf-8');

// Initialize client from JSON configuration content
const client = Client.fromJsonConfig(fileContent);
```

See the [Configuration-Based Client Initialization](https://www.github.com/WasifMatic/link-payments-js-sdk/tree/2.2.0/doc/configuration-based-client-initialization.md) section for details.

### Environment-Based Client Initialization

```ts
import * as dotenv from 'dotenv';
import * as path from 'path';
import * as fs from 'fs';
import { Client } from 'link-payments-sdk';

// Optional - Provide absolute path for the .env file
const absolutePath = path.resolve('./.env');

if (fs.existsSync(absolutePath)) {
  // Load environment variables from .env file
  dotenv.config({ path: absolutePath, override: true });
}

// Initialize client using environment variables
const client = Client.fromEnvironment(process.env);
```

See the [Environment-Based Client Initialization](https://www.github.com/WasifMatic/link-payments-js-sdk/tree/2.2.0/doc/environment-based-client-initialization.md) section for details.

## List of APIs

* [Simple Calculator](https://www.github.com/WasifMatic/link-payments-js-sdk/tree/2.2.0/doc/controllers/simple-calculator.md)

## SDK Infrastructure

### Configuration

* [HttpClientOptions](https://www.github.com/WasifMatic/link-payments-js-sdk/tree/2.2.0/doc/http-client-options.md)
* [RetryConfiguration](https://www.github.com/WasifMatic/link-payments-js-sdk/tree/2.2.0/doc/retry-configuration.md)
* [ProxySettings](https://www.github.com/WasifMatic/link-payments-js-sdk/tree/2.2.0/doc/proxy-settings.md)
* [Configuration-Based Client Initialization](https://www.github.com/WasifMatic/link-payments-js-sdk/tree/2.2.0/doc/configuration-based-client-initialization.md)
* [Environment-Based Client Initialization](https://www.github.com/WasifMatic/link-payments-js-sdk/tree/2.2.0/doc/environment-based-client-initialization.md)
* [PartialLoggingOptions](https://www.github.com/WasifMatic/link-payments-js-sdk/tree/2.2.0/doc/partial-logging-options.md)
* [PartialRequestLoggingOptions](https://www.github.com/WasifMatic/link-payments-js-sdk/tree/2.2.0/doc/partial-request-logging-options.md)
* [PartialResponseLoggingOptions](https://www.github.com/WasifMatic/link-payments-js-sdk/tree/2.2.0/doc/partial-response-logging-options.md)
* [LoggerInterface](https://www.github.com/WasifMatic/link-payments-js-sdk/tree/2.2.0/doc/logger-interface.md)

### HTTP

* [HttpRequest](https://www.github.com/WasifMatic/link-payments-js-sdk/tree/2.2.0/doc/http-request.md)

### Utilities

* [ApiResponse](https://www.github.com/WasifMatic/link-payments-js-sdk/tree/2.2.0/doc/api-response.md)
* [ApiError](https://www.github.com/WasifMatic/link-payments-js-sdk/tree/2.2.0/doc/api-error.md)

