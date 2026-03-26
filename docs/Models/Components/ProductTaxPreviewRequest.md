# ProductTaxPreviewRequest

Request body for previewing tax on a product price.


## Fields

| Field                                                  | Type                                                   | Required                                               | Description                                            |
| ------------------------------------------------------ | ------------------------------------------------------ | ------------------------------------------------------ | ------------------------------------------------------ |
| `amount`                                               | *int*                                                  | :heavy_check_mark:                                     | Amount in smallest currency unit (e.g. cents for USD). |
| `currency`                                             | *string*                                               | :heavy_check_mark:                                     | ISO 4217 currency code (e.g. 'usd').                   |
| `country`                                              | *string*                                               | :heavy_check_mark:                                     | ISO 3166-1 alpha-2 country code (e.g. 'AU').           |
| `quantity`                                             | *?int*                                                 | :heavy_minus_sign:                                     | Unit quantity for the preview calculation.             |
| `state`                                                | *?string*                                              | :heavy_minus_sign:                                     | State/province code for US/CA (e.g. 'WA' or 'US-WA').  |