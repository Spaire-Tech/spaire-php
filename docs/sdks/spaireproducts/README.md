# Products.Products

## Overview

### Available Operations

* [previewTax](#previewtax) - Preview Tax

## previewTax

Estimate tax for a product price given a customer location and quantity.
Uses the configured tax provider (Stripe Tax) to calculate applicable taxes.

**Scopes**: `products:read` `products:write`

### Example Usage

<!-- UsageSnippet language="php" operationID="products:products:preview_tax" method="post" path="/v1/products/tax-preview" -->
```php
declare(strict_types=1);

require 'vendor/autoload.php';

use Spaire;
use Spaire\Models\Components;

$sdk = Spaire\Spaire::builder()
    ->setSecurity(
        '<YOUR_BEARER_TOKEN_HERE>'
    )
    ->build();

$request = new Components\ProductTaxPreviewRequest(
    amount: 428098,
    currency: 'Kina',
    country: 'Guatemala',
);

$response = $sdk->products->products->previewTax(
    request: $request
);

if ($response->productTaxPreviewResponse !== null) {
    // handle response
}
```

### Parameters

| Parameter                                                                                  | Type                                                                                       | Required                                                                                   | Description                                                                                |
| ------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------ |
| `$request`                                                                                 | [Components\ProductTaxPreviewRequest](../../Models/Components/ProductTaxPreviewRequest.md) | :heavy_check_mark:                                                                         | The request object to use for the request.                                                 |

### Response

**[?Operations\ProductsProductsPreviewTaxResponse](../../Models/Operations/ProductsProductsPreviewTaxResponse.md)**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| Errors\HTTPValidationError | 422                        | application/json           |
| Errors\APIException        | 4XX, 5XX                   | \*/\*                      |