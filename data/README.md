# Data

The raw CSV (~95 MB) is not committed. Download it from either source:

- Mendeley Data (original, CC BY 4.0): https://data.mendeley.com/datasets/8gx2fvg2k6/5
- Kaggle mirror: https://www.kaggle.com/datasets/shashwatwork/dataco-smart-supply-chain-for-big-data-analysis

Save `DataCoSupplyChainDataset.csv` in this folder. Read it with `encoding="latin-1"`.
`DescriptionDataCoSupplyChain.csv` (field descriptions) and `tokenized_access_logs.csv` (clickstream, not used here) are in the same download.

Citation: Constante, F., Silva, F., Pereira, A. (2019). DataCo SMART SUPPLY CHAIN FOR BIG DATA ANALYSIS. Mendeley Data, V5. doi:10.17632/8gx2fvg2k6.5

## Key columns

| Column | Meaning |
|---|---|
| `Order Id` / `Order Item Id` | Order and line item (180,519 items in 65,752 orders) |
| `Order Customer Id` | Customer (20,652) |
| `Type` | Payment type: DEBIT, TRANSFER, PAYMENT, CASH |
| `Days for shipping (real)` / `Days for shipment (scheduled)` | Actual and promised shipping days |
| `Delivery Status` | Advance shipping, Shipping on time, Late delivery, Shipping canceled |
| `Late_delivery_risk` | 1 = late delivery |
| `Shipping Mode` | Standard, Second, First Class, Same Day |
| `Order Item Discount Rate` | Discount rate on the item (0–25%) |
| `Sales per customer` | Item sales after discount |
| `Benefit per order` / `Order Profit Per Order` | Profit for the item |
| `Order Status` | COMPLETE, CLOSED, PENDING, CANCELED, SUSPECTED_FRAUD, ... |
| `Order Region`, `Market` | Delivery region and market |

Customer e-mail and password are masked (`XXXXXXXXX`) in the source; names and addresses are synthetic.
