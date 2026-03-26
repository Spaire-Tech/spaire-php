# ClientInvoiceLineItemPreview

Relaxed line item for preview — allows zero amounts for in-progress editing.


## Fields

| Field                                        | Type                                         | Required                                     | Description                                  |
| -------------------------------------------- | -------------------------------------------- | -------------------------------------------- | -------------------------------------------- |
| `description`                                | *?string*                                    | :heavy_minus_sign:                           | Line item description.                       |
| `quantity`                                   | *?int*                                       | :heavy_minus_sign:                           | Quantity.                                    |
| `unitAmount`                                 | *?int*                                       | :heavy_minus_sign:                           | Unit price in cents (0 allowed for preview). |