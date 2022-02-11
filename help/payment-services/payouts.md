---
title: Payouts report
description: Use the Payouts report for full transparency into the payment amount, processed volume, and detailed reporting on the transaction level for financial reconciliation.
role: User
level: Intermediate
exl-id: f3f99474-cd28-4c8f-b0ea-dca8e014b108
---
# Payouts report

The Payouts report shows comprehensive payout information at-a-glance, allowing you full transparency into the payment amount, processed volume, and detailed reporting on the transaction level for financial reconciliation.

You don't have to open multiple dashboards or views to cross-reference orders and payments or reconcile accounts. Payment Services for Adobe Commerce and Magento Open Source enables you to take all these actions from one place---Payouts report---so that you can view and manage your payouts efficiently.

See linked Magento order and transaction IDs, transaction amounts, payment method per transaction, and more, all within the Payouts report in the Admin.

You can download payout transactions in a .csv file format for use in existing accounting or order management software.

>[!NOTE]
>
>The data shown in this table is sorted in descending order (`DESC`) by default using the `TRANS DATE`. The `TRANS DATE` is the date and time when the transaction was initiated.

## Availability

On the _Admin_ sidebar, go to **Sales** > **Payment Services** > **Payouts**.

![Payout transactions in the Admin](assets/payouts-report.png)

## Select data source

In the Payouts report view, you can select the data source---_Live_ or _Sandbox_---for which you want to see report results.

![Data sources selection](assets/datasource.png)

If _Live_ is the selected data source, you can see report information for your live stores. If _Sandbox_ is the selected data source, you can see report information for your Sandbox environment.

Data source selections work as follows:

* If you do not have any stores that are in Live mode, the data source selection defaults to _Sandbox_.
* If you have any stores (one or multiple) in Live mode, the data source selection defaults to _Live_.
* Report exports always honor the data source selection.

To select the data source for your Order Payment Status report:

1. On the _Admin_ sidebar, go to **Sales** > **Payment Services** > **Payouts**.
1. Click the **Data source** dropdown.
1. Select _Live_ or _Sandbox_.

   The report results regenerate based on the data source selected.

## View transactions

By default, 30 days of transactions are shown in the grid.

The number of rows returned in a search, or shown in the default 30 days of transactions, are shown above the Payouts view grid alongside the Transaction dates calendar selector filter.

Scroll to the left and right to view [information for each payout transaction](#column-descriptions) in the daily report, including transaction date, reference ID, invoice number, and payment method details.

### Customize transactions timeframe

From the Payouts view, you can customize the timeframe for the payout transactions you want to view by entering specific dates or selecting a date range from the date picker:

1. On the _Admin_ sidebar, go to **Sales** > **Payment Services** > **Payouts**.
1. Click the Transaction dates calendar selector filter.
1. Choose the applicable date range.
1. View the payouts statuses in the grid for your specified dates.

## Download transactions

You can download a .csv file containing all the transactions visible in the Payouts view grid.

1. On the _Admin_ sidebar, go to **Sales** > **Payment Services** > **Payouts**.
1. [Customize the date range timeframe for your transactions](#customize-transactions-timeframe).
1. Click the _Download_ (![](assets/icon-download.png) icon.

Your payout transactions are downloaded in a .csv format.

## Transactions information

The Payouts view shows extensive info for each transaction shown in the grid.

### Column descriptions

Payout reports include the following information.

| Column | Description |
| ------------ | -------------------- |
| Provider | Payment provider |
| Provider trans | Transaction ID |
| Trans date | Date and time transaction was initiated |
| Type | Transaction type---*PAYMENT*, *AUTH*, *BONUS*, *CHARGEBACK*, *CORRECTION*, *CURRENCY_CONVERSATION*, *DEPOSIT*, *DISBURSEMENT*, *DISPUTE*, *FEES*, *HOLD*, *HOLD_RELEASE*, *INCENTIVES*, *OTHERS*, *RECOUP*, *REFUND*, *REVERSAL*, *WITHDRAWAL* <br> <br>See [Transaction types](#transaction-types) for more information. |
| Status | Current status of the transaction---*SUCCESS*, *DENIED*, *PENDING* |
| Code | Transaction code that indicates either Credit (*CR*) or Debit (*DR*) |
| Reference ID | Original transaction ID for which this event is related |
| Invoice | Invoice ID (one per order) of the transaction |
| Commerce order | Commerce order ID <br> <br>To see related [order info](https://docs.magento.com/user-guide/sales/orders.html){target="_blank"}, click the ID. |
| Commerce trans | Commerce transaction ID <br> <br>To see related [transaction info](https://docs.magento.com/user-guide/sales/transactions.html){target="_blank"}, click the ID. |
| Pay method | Credit card type---*BANK*, *PAYPAL*, *CREDIT_CARD*---and associated card provider (such as *Visa* or *MasterCard*) |
| Trans amt | Amount of the transaction |
| Cur | Currency unit for transaction amount |
| Pending | Amount yet to be disbursed |
| Cur | Currency unit for the pending amount |
| Seller amt | Amount of funds transferred to or from a customer <br> <br>Funds moving out of the seller account show a dash (-) prefix. |
| Cur | Currency unit for the seller amount |
| Partner fee | Partner fees associated with the transaction <br> <br>Funds moving out of the partner fee account show a dash (-) prefix. |
| Cur | Currency unit for the partner fee |
| Prov fees | Fees associated with the transaction <br> <br>Funds moving out of the provider's fee account show a dash (-) prefix. |
| Cur | Currency unit for the provider fee |
| Fee % | Percentage of the transaction amount charged as a fee |
| Fixed fee | Fixed provider fee amount |
| Chbk fee | Chargeback fee associated with the transaction <br> <br>A dash (-) prefix indicates that the chargeback fee was reversed. |
| Cur | Currency unit for the chargeback fee |
| Hold amt | Amount put on hold or released from hold <br> <br>A dash (-) prefix indicates that on-hold funds are being released. |
| Cur | Currency unit for the hold amount |
| Recoup amt | Amount recouped from the recoup account <br> <br>Funds moving out of the recoup account show a dash (-) prefix. |
| Cur | Currency unit for the recoup amount |

### Transaction types

These transaction types may be noted in the payout transactions.

| Report | Description |
| ------------ | -------------------- |
| PAYMENT | Money moved between a buyer and a seller for an order |
| AUTH | Authorization and authorization void transactions |
| BONUS | -- |
| CHARGEBACK | Chargeback fee and chargeback fee reversal transactions |
| CORRECTION | -- |
| CURRENCY_CONVERSION | -- |
| DEPOSIT | -- |
| DISBURSEMENT | -- |
| DISPUTE | -- |
| FEES | Partner fees, payment fees, and fee reversal transactions |
| HOLD | -- |
| HOLD_RELEASE | -- |
| INCENTIVES | -- |
| OTHERS | -- |
| RECOUP | Recoups from bank or loss accounts |
| REFUND | -- |
| REVERSAL | -- |
| WITHDRAWAL | -- |