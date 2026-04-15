# Simple Calculator

```ts
const simpleCalculatorApi = new SimpleCalculatorApi(client);
```

## Class Name

`SimpleCalculatorApi`


# Calculate

Calculates the expression using the specified operation.

```ts
async calculate(
  operation: OperationType,
  x: number,
  y: number,
  requestOptions?: RequestOptions
): Promise<ApiResponse<number>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `operation` | [`OperationType`](../../doc/models/operation-type.md) | Template, Required | The operator to apply on the variables |
| `x` | `number` | Query, Required | The LHS value |
| `y` | `number` | Query, Required | The RHS value |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type `number`.

## Example Usage

```ts
const operation = OperationType.Sum;

const x = 222.14;

const y = 165.14;

try {
  const response = await simpleCalculatorApi.calculate(
    operation,
    x,
    y
  );

  // Extracting fully parsed response body.
  console.log(response.result);

  // Extracting response status code.
  console.log(response.statusCode);
  // Extracting response headers.
  console.log(response.headers);
  // Extracting response body of type `string | Stream`
  console.log(response.body);
} catch (error) {
  if (error instanceof ApiError) {
    // Extracting response error status code.
    console.log(error.statusCode);
    // Extracting response error headers.
    console.log(error.headers);
    // Extracting response error body of type `string | Stream`.
    console.log(error.body);
  }
}
```

