# ClientInvoiceLineItemSchema


## Fields

| Field                                                         | Type                                                          | Required                                                      | Description                                                   |
| ------------------------------------------------------------- | ------------------------------------------------------------- | ------------------------------------------------------------- | ------------------------------------------------------------- |
| `id`                                                          | *string*                                                      | :heavy_check_mark:                                            | The ID of the object.                                         |
| `createdAt`                                                   | [\DateTime](https://www.php.net/manual/en/class.datetime.php) | :heavy_check_mark:                                            | Creation timestamp of the object.                             |
| `modifiedAt`                                                  | [\DateTime](https://www.php.net/manual/en/class.datetime.php) | :heavy_check_mark:                                            | Last modification timestamp of the object.                    |
| `clientInvoiceId`                                             | *string*                                                      | :heavy_check_mark:                                            | N/A                                                           |
| `stripeInvoiceItemId`                                         | *string*                                                      | :heavy_check_mark:                                            | N/A                                                           |
| `description`                                                 | *string*                                                      | :heavy_check_mark:                                            | N/A                                                           |
| `quantity`                                                    | *int*                                                         | :heavy_check_mark:                                            | N/A                                                           |
| `unitAmount`                                                  | *int*                                                         | :heavy_check_mark:                                            | N/A                                                           |
| `currency`                                                    | *string*                                                      | :heavy_check_mark:                                            | N/A                                                           |
| `amount`                                                      | *int*                                                         | :heavy_check_mark:                                            | N/A                                                           |
| `taxAmount`                                                   | *int*                                                         | :heavy_check_mark:                                            | N/A                                                           |