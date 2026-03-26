# ProductTaxPreviewResponse

Tax preview result for a product price.


## Fields

| Field                                                                   | Type                                                                    | Required                                                                | Description                                                             |
| ----------------------------------------------------------------------- | ----------------------------------------------------------------------- | ----------------------------------------------------------------------- | ----------------------------------------------------------------------- |
| `subtotal`                                                              | *int*                                                                   | :heavy_check_mark:                                                      | N/A                                                                     |
| `taxAmount`                                                             | *int*                                                                   | :heavy_check_mark:                                                      | N/A                                                                     |
| `total`                                                                 | *int*                                                                   | :heavy_check_mark:                                                      | N/A                                                                     |
| `currency`                                                              | *string*                                                                | :heavy_check_mark:                                                      | N/A                                                                     |
| `quantity`                                                              | *int*                                                                   | :heavy_check_mark:                                                      | N/A                                                                     |
| `taxRate`                                                               | [?Components\TaxRatePreview](../../Models/Components/TaxRatePreview.md) | :heavy_minus_sign:                                                      | N/A                                                                     |
| `taxabilityReason`                                                      | *?string*                                                               | :heavy_minus_sign:                                                      | N/A                                                                     |