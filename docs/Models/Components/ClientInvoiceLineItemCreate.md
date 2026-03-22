# ClientInvoiceLineItemCreate


## Fields

| Field                                                  | Type                                                   | Required                                               | Description                                            |
| ------------------------------------------------------ | ------------------------------------------------------ | ------------------------------------------------------ | ------------------------------------------------------ |
| `description`                                          | *string*                                               | :heavy_check_mark:                                     | Line item description shown on the invoice.            |
| `quantity`                                             | *?int*                                                 | :heavy_minus_sign:                                     | Quantity.                                              |
| `unitAmount`                                           | *int*                                                  | :heavy_check_mark:                                     | Unit price in the smallest currency unit (e.g. cents). |