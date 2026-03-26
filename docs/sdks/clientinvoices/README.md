# ClientInvoices

## Overview

### Available Operations

* [listClientInvoices](#listclientinvoices) - List Client Invoices
* [createClientInvoice](#createclientinvoice) - Create Client Invoice
* [previewClientInvoicePdf](#previewclientinvoicepdf) - Preview Client Invoice PDF
* [getClientInvoice](#getclientinvoice) - Get Client Invoice
* [downloadClientInvoicePdf](#downloadclientinvoicepdf) - Download Client Invoice PDF
* [finalizeClientInvoice](#finalizeclientinvoice) - Finalize Client Invoice
* [sendClientInvoice](#sendclientinvoice) - Send Client Invoice
* [markClientInvoicePaid](#markclientinvoicepaid) - Mark Client Invoice as Paid
* [voidClientInvoice](#voidclientinvoice) - Void Client Invoice

## listClientInvoices

List client invoices for the authenticated organization.

**Scopes**: `client_invoices:read`

### Example Usage

<!-- UsageSnippet language="php" operationID="client_invoices:list_client_invoices" method="get" path="/v1/client-invoices/" -->
```php
declare(strict_types=1);

require 'vendor/autoload.php';

use Spaire;

$sdk = Spaire\Spaire::builder()
    ->setSecurity(
        '<YOUR_BEARER_TOKEN_HERE>'
    )
    ->build();



$responses = $sdk->clientInvoices->listClientInvoices(
    page: 1,
    limit: 10

);


foreach ($responses as $response) {
    if ($response->statusCode === 200) {
        // handle response
    }
}
```

### Parameters

| Parameter                                                                                                                                                               | Type                                                                                                                                                                    | Required                                                                                                                                                                | Description                                                                                                                                                             |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `page`                                                                                                                                                                  | *?int*                                                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                      | Page number, defaults to 1.                                                                                                                                             |
| `limit`                                                                                                                                                                 | *?int*                                                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                      | Size of a page, defaults to 10. Maximum is 100.                                                                                                                         |
| `sorting`                                                                                                                                                               | array<[Components\ClientInvoiceSortProperty](../../Models/Components/ClientInvoiceSortProperty.md)>                                                                     | :heavy_minus_sign:                                                                                                                                                      | Sorting criterion. Several criteria can be used simultaneously and will be applied in order. Add a minus sign `-` before the criteria name to sort by descending order. |

### Response

**[?Operations\ClientInvoicesListClientInvoicesResponse](../../Models/Operations/ClientInvoicesListClientInvoicesResponse.md)**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| Errors\HTTPValidationError | 422                        | application/json           |
| Errors\APIException        | 4XX, 5XX                   | \*/\*                      |

## createClientInvoice

Create a new draft client invoice. Tax is calculated automatically.

**Scopes**: `client_invoices:write`

### Example Usage

<!-- UsageSnippet language="php" operationID="client_invoices:create_client_invoice" method="post" path="/v1/client-invoices/" -->
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

$request = new Components\ClientInvoiceCreate(
    customerId: '<value>',
    currency: 'Gibraltar Pound',
    lineItems: [],
);

$response = $sdk->clientInvoices->createClientInvoice(
    request: $request
);

if ($response->clientInvoiceSchema !== null) {
    // handle response
}
```

### Parameters

| Parameter                                                                        | Type                                                                             | Required                                                                         | Description                                                                      |
| -------------------------------------------------------------------------------- | -------------------------------------------------------------------------------- | -------------------------------------------------------------------------------- | -------------------------------------------------------------------------------- |
| `$request`                                                                       | [Components\ClientInvoiceCreate](../../Models/Components/ClientInvoiceCreate.md) | :heavy_check_mark:                                                               | The request object to use for the request.                                       |

### Response

**[?Operations\ClientInvoicesCreateClientInvoiceResponse](../../Models/Operations/ClientInvoicesCreateClientInvoiceResponse.md)**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| Errors\HTTPValidationError | 422                        | application/json           |
| Errors\APIException        | 4XX, 5XX                   | \*/\*                      |

## previewClientInvoicePdf

Generate a real PDF preview from form data without creating anything.

**Scopes**: `client_invoices:read`

### Example Usage

<!-- UsageSnippet language="php" operationID="client_invoices:preview_client_invoice_pdf" method="post" path="/v1/client-invoices/preview-pdf" -->
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

$request = new Components\ClientInvoicePreviewRequest(
    organizationId: '<value>',
    currency: 'Baht',
    lineItems: [],
);

$response = $sdk->clientInvoices->previewClientInvoicePdf(
    request: $request
);

if ($response->statusCode === 200) {
    // handle response
}
```

### Parameters

| Parameter                                                                                        | Type                                                                                             | Required                                                                                         | Description                                                                                      |
| ------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------ |
| `$request`                                                                                       | [Components\ClientInvoicePreviewRequest](../../Models/Components/ClientInvoicePreviewRequest.md) | :heavy_check_mark:                                                                               | The request object to use for the request.                                                       |

### Response

**[?Operations\ClientInvoicesPreviewClientInvoicePdfResponse](../../Models/Operations/ClientInvoicesPreviewClientInvoicePdfResponse.md)**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| Errors\HTTPValidationError | 422                        | application/json           |
| Errors\APIException        | 4XX, 5XX                   | \*/\*                      |

## getClientInvoice

Get a client invoice by ID.

**Scopes**: `client_invoices:read`

### Example Usage

<!-- UsageSnippet language="php" operationID="client_invoices:get_client_invoice" method="get" path="/v1/client-invoices/{id}" -->
```php
declare(strict_types=1);

require 'vendor/autoload.php';

use Spaire;

$sdk = Spaire\Spaire::builder()
    ->setSecurity(
        '<YOUR_BEARER_TOKEN_HERE>'
    )
    ->build();



$response = $sdk->clientInvoices->getClientInvoice(
    id: '<value>'
);

if ($response->clientInvoiceSchema !== null) {
    // handle response
}
```

### Parameters

| Parameter          | Type               | Required           | Description        |
| ------------------ | ------------------ | ------------------ | ------------------ |
| `id`               | *string*           | :heavy_check_mark: | N/A                |

### Response

**[?Operations\ClientInvoicesGetClientInvoiceResponse](../../Models/Operations/ClientInvoicesGetClientInvoiceResponse.md)**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| Errors\HTTPValidationError | 422                        | application/json           |
| Errors\APIException        | 4XX, 5XX                   | \*/\*                      |

## downloadClientInvoicePdf

Generate and download a PDF for the given client invoice.

**Scopes**: `client_invoices:read`

### Example Usage

<!-- UsageSnippet language="php" operationID="client_invoices:download_client_invoice_pdf" method="get" path="/v1/client-invoices/{id}/pdf" -->
```php
declare(strict_types=1);

require 'vendor/autoload.php';

use Spaire;

$sdk = Spaire\Spaire::builder()
    ->setSecurity(
        '<YOUR_BEARER_TOKEN_HERE>'
    )
    ->build();



$response = $sdk->clientInvoices->downloadClientInvoicePdf(
    id: '<value>'
);

if ($response->statusCode === 200) {
    // handle response
}
```

### Parameters

| Parameter          | Type               | Required           | Description        |
| ------------------ | ------------------ | ------------------ | ------------------ |
| `id`               | *string*           | :heavy_check_mark: | N/A                |

### Response

**[?Operations\ClientInvoicesDownloadClientInvoicePdfResponse](../../Models/Operations/ClientInvoicesDownloadClientInvoicePdfResponse.md)**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| Errors\HTTPValidationError | 422                        | application/json           |
| Errors\APIException        | 4XX, 5XX                   | \*/\*                      |

## finalizeClientInvoice

Finalize a draft invoice (generates PDF) without sending the email.
Status moves from draft → open. Use this to preview the invoice before sending.

**Scopes**: `client_invoices:write`

### Example Usage

<!-- UsageSnippet language="php" operationID="client_invoices:finalize_client_invoice" method="post" path="/v1/client-invoices/{id}/finalize" -->
```php
declare(strict_types=1);

require 'vendor/autoload.php';

use Spaire;

$sdk = Spaire\Spaire::builder()
    ->setSecurity(
        '<YOUR_BEARER_TOKEN_HERE>'
    )
    ->build();



$response = $sdk->clientInvoices->finalizeClientInvoice(
    id: '<value>'
);

if ($response->clientInvoiceSchema !== null) {
    // handle response
}
```

### Parameters

| Parameter          | Type               | Required           | Description        |
| ------------------ | ------------------ | ------------------ | ------------------ |
| `id`               | *string*           | :heavy_check_mark: | N/A                |

### Response

**[?Operations\ClientInvoicesFinalizeClientInvoiceResponse](../../Models/Operations/ClientInvoicesFinalizeClientInvoiceResponse.md)**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| Errors\HTTPValidationError | 422                        | application/json           |
| Errors\APIException        | 4XX, 5XX                   | \*/\*                      |

## sendClientInvoice

Finalize and send a draft invoice to the customer via Stripe.

**Scopes**: `client_invoices:write`

### Example Usage

<!-- UsageSnippet language="php" operationID="client_invoices:send_client_invoice" method="post" path="/v1/client-invoices/{id}/send" -->
```php
declare(strict_types=1);

require 'vendor/autoload.php';

use Spaire;

$sdk = Spaire\Spaire::builder()
    ->setSecurity(
        '<YOUR_BEARER_TOKEN_HERE>'
    )
    ->build();



$response = $sdk->clientInvoices->sendClientInvoice(
    id: '<value>'
);

if ($response->clientInvoiceSchema !== null) {
    // handle response
}
```

### Parameters

| Parameter          | Type               | Required           | Description        |
| ------------------ | ------------------ | ------------------ | ------------------ |
| `id`               | *string*           | :heavy_check_mark: | N/A                |

### Response

**[?Operations\ClientInvoicesSendClientInvoiceResponse](../../Models/Operations/ClientInvoicesSendClientInvoiceResponse.md)**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| Errors\HTTPValidationError | 422                        | application/json           |
| Errors\APIException        | 4XX, 5XX                   | \*/\*                      |

## markClientInvoicePaid

Mark a draft or open invoice as paid manually without going through Stripe.

**Scopes**: `client_invoices:write`

### Example Usage

<!-- UsageSnippet language="php" operationID="client_invoices:mark_client_invoice_paid" method="post" path="/v1/client-invoices/{id}/mark-paid" -->
```php
declare(strict_types=1);

require 'vendor/autoload.php';

use Spaire;

$sdk = Spaire\Spaire::builder()
    ->setSecurity(
        '<YOUR_BEARER_TOKEN_HERE>'
    )
    ->build();



$response = $sdk->clientInvoices->markClientInvoicePaid(
    id: '<value>'
);

if ($response->clientInvoiceSchema !== null) {
    // handle response
}
```

### Parameters

| Parameter          | Type               | Required           | Description        |
| ------------------ | ------------------ | ------------------ | ------------------ |
| `id`               | *string*           | :heavy_check_mark: | N/A                |

### Response

**[?Operations\ClientInvoicesMarkClientInvoicePaidResponse](../../Models/Operations/ClientInvoicesMarkClientInvoicePaidResponse.md)**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| Errors\HTTPValidationError | 422                        | application/json           |
| Errors\APIException        | 4XX, 5XX                   | \*/\*                      |

## voidClientInvoice

Void a draft or open invoice.

**Scopes**: `client_invoices:write`

### Example Usage

<!-- UsageSnippet language="php" operationID="client_invoices:void_client_invoice" method="post" path="/v1/client-invoices/{id}/void" -->
```php
declare(strict_types=1);

require 'vendor/autoload.php';

use Spaire;

$sdk = Spaire\Spaire::builder()
    ->setSecurity(
        '<YOUR_BEARER_TOKEN_HERE>'
    )
    ->build();



$response = $sdk->clientInvoices->voidClientInvoice(
    id: '<value>'
);

if ($response->clientInvoiceSchema !== null) {
    // handle response
}
```

### Parameters

| Parameter          | Type               | Required           | Description        |
| ------------------ | ------------------ | ------------------ | ------------------ |
| `id`               | *string*           | :heavy_check_mark: | N/A                |

### Response

**[?Operations\ClientInvoicesVoidClientInvoiceResponse](../../Models/Operations/ClientInvoicesVoidClientInvoiceResponse.md)**

### Errors

| Error Type                 | Status Code                | Content Type               |
| -------------------------- | -------------------------- | -------------------------- |
| Errors\HTTPValidationError | 422                        | application/json           |
| Errors\APIException        | 4XX, 5XX                   | \*/\*                      |