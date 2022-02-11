---
title: Order payment status report
description: Use the Order payment status report for gain visibility to the payment status of your orders and identify any potential issues.
role: User
level: Intermediate
exl-id: 192e47b9-d52b-4dcf-a720-38459156fda4
---
# Order payment status report

The Order payment status report helps you easily understand where a specific order is within the order to cash process flow. This report allows you to quickly view the payment status of your orders and identify any potential issues.

![Payment Services extension Admin view](assets/admin-view.png)

You don't have to open multiple views to manually cross reference orders and payments. Payment Services for Adobe Commerce and Magento Open Source enables you to get a bird's-eye-view of your orders and payments---all within the Order payment status report.

See payment statuses, invoiced and shipped statuses, refund statuses, dispute statuses, and more, all within this report in the Admin.

You can download Order payment status transactions in a .csv file format for use in existing accounting or order management software.

>[!NOTE]
>
>You cannot view financial reports if you have not [onboarded and activated Live mode](production.md#enable-live-payments) for Payment Services.

## Data used in the report

The Payment Services module uses order data, and combine it with aggregated payment data from other sources (including PayPal), to provide meaningful and highly useful reports.

Order data is exported and persisted in the payment service. When you [change or add order statuses](https://docs.magento.com/user-guide/sales/order-status-custom.html){target="_blank"} or [edit a store view](https://docs.magento.com/user-guide/stores/stores-all-view-edit.html){target="_blank"}, [store](https://docs.magento.com/user-guide/stores/store-information.html){target="_blank"}, or website name, that data is combined with payment data and the Order payment status report is populated with the combined info.

There are two steps in this process:

1. The index is changed data either `ON SAVE` (every time order info or store info is changed) or `BY SCHEDULE` (on a pre-configured cron schedule), depending on how it is configured in [Index Management](https://docs.magento.com/user-guide/system/index-management.html){target="_blank"} in the Admin.

    By default, data indexation occurs `ON SAVE`, which means that whenever something changes in the order, the order status, the store view, the store, or the website, the reindexation process happens immediately.

1. The indexed data is sent to the payment service, which then populates into the Order payment status report.

The only data that is exported and collated for reporting purposes is data used by the Order payment status report.

>[!NOTE]
>
>The data shown in this table is sorted in descending order (`DESC`) by default using the `ORDER DATE`. The `ORDER DATE` is the date timestamp when the order was created.

### Configure data export

Even though, by default, reindexing happens in `ON SAVE` mode, it is recommended that you index in `BY SCHEDULE` mode. The `BY SCHEDULE` index runs on a cron schedule of one minute, and any changed data appears in your Order status report within two minutes of any data change. This scheduled reindexing helps you reduce any strain on your store, especially if you have a large volume of incoming orders, because it happens on a schedule (not as each order is placed).

You can change the index mode---`ON SAVE` or `BY SCHEDULE`---[in the Admin](https://docs.magento.com/user-guide/system/index-management.html#change-the-index-mode){target="_blank"}.

To learn how to configure the data export, see [Command-line configuration](configure-cli.md#configure-data-export).

## Availability

On the _Admin_ sidebar, go to **Sales** > **Payment Services** > **Order payment status** to see the payment statuses for your orders.

![Order payment statuses in the Admin](assets/order-payment-status-report.png)

## Select data source

In the Order payment status report view, you can select the data source---_Live_ or _Sandbox_---for which you want to see report results.

![Data sources selection](assets/datasource.png)

If _Live_ is the selected data source, you can see report information for your stores that use Payment Services in _Live_ mode. If _Sandbox_ is the selected data source, you can see report information for your Sandbox environment.

Data source selections work as follows:

* If you do not have any stores that use Payment Services in Live mode, the data source selection defaults to _Sandbox_.
* If you have any stores (one or multiple) that use Payment Services in Live mode, the data source selection defaults to _Live_.
* Report exports always honor the data source selection.

To select the data source for your Order Payment Status report:

1. On the _Admin_ sidebar, go to **Sales** > **Payment Services** > **Order payment status**.
1. Click the **Data source** dropdown.
1. Select _Live_ or _Sandbox_.

   The report results regenerate based on the data source selected.

## Customize dates timeframe

From the Order payment status report view, you can customize the timeframe of the statuses you want to view by selecting specific dates. By default, 30 days of order payment statuses are shown in the grid.

1. On the _Admin_ sidebar, go to **Sales** > **Payment Services** > **Order payment status**.
1. Click the **Order dates** calendar selector filter.
1. Choose the applicable date range.
1. View the order payment statuses for your specified dates in the grid.

## View statuses

By default, 30 days of order payment statuses are shown in the grid.

Scroll to the left and right to view [order payment status information](#column-descriptions), including order date, authorized date, invoiced, shipped, pay status, and more.

The number of rows returned in a search, or shown in the default 30 days of order payment statuses, are shown above the Order payment status view grid alongside the Order dates calendar selector filter.

## Update report data

The Order payment status report view shows a _Last updated_ timestamp that shows the last time that the report information was updated. By default, Order payment status report data is auto-refreshed every three hours.

You can also manually force a refresh of the Order payment status report data to see the most up-to-date report information.

1. On the _Admin_ sidebar, go to **Sales** > **Payment Services** > **Order payment status**.
1. Click the _Refresh_ icon (![refresh icon](assets/refresh-button-med.png)).

   The Order payment status report data is refreshed, an *Update complete* confirmation appears, and the latest information is present in the grid.

## Download order payment statuses

You can download a .csv file with all statuses visible in the Order payment status view grid, whether you are viewing the default 30 days of statuses or a customized timeframe.

1. On the _Admin_ sidebar, go to **Sales** > **Payment Services** > **Order payment status**.
1. If you want to see statuses for a timeframe other than the last 30 days, [customize the date range timeframe for your statuses](#customize-dates-timeframe).
1. Click the _Download_ (![](assets/icon-download.png)) icon.

Your order payment statuses are downloaded in a .csv format.

<!-- ## Default order payment status timeframes

These order payment status timeframes are currently available in Payment Services.

| Report       | Description          |
| ------------ | -------------------- |
| Yesterday | Available from the Order payment status dates selector, this shows information for the prior date. |
| | Today | Available from the Order payment status dates selector, this shows information for the current day. |
| Last 7 days | Available from the Order payment status dates selector, this shows information for the last seven days. |
| Last 30 days | Available from the Order payment status dates selector and by default in the Order payment statuses view, this shows information for the last 30 days. |
| Last 90 days | Available from the Order payment status dates selector, this shows information for the last 90 days. |
| Year to date | Available from the Order payment status dates selector, this shows information for the the entire year to date. |
| Custom range | Available from the Order payment status dates selector, this can be filtered to show a custom date range. |
-->

## Order payment status information

The Order payment status view shows extensive info for each status shown in the grid.

### Column descriptions

Order payment status reports include the following information.

| Column | Description |
| ------------ | -------------------- |
| Order ID | Commerce order ID<br> <br>To see related [order info](https://docs.magento.com/user-guide/sales/orders.html){target="_blank"}, click the ID. |
| Order Date | Order date timestamp |
| Authorized Date | Date timestamp of payment authorization |
| Order Status | Current Commerce [order status](https://docs.magento.com/user-guide/sales/order-status.html){target="_blank"} |
| Invoiced | Invoice status of order---*No*, *Partial*, or *Yes* |
| Shipped | Shipping status of order---*No*, *Partial*, or *Yes* |
| Order Amt | Grand total amount of the order |
| Cur | Currency type of order |
| Pay Status | Status of payment for a specific order |
| Paid Amt | Amount paid on an order |
| Cur| Currency type of the amount paid on an order |
| Refund Status | Status of a refund on an order (such as information from returns, RMAs, and credit memos)---   *Requires refund*, *Refund requested*, *Refunded*, *Refund failed*, or *Voided* |
| Refund Amount | Total of refunded amount for an order |
| Cur | Currency type of the amount refunded for an order |
| Dispute Status | Status of any dispute on an order (information from disputes and chargebacks)---*New*, *Representment*, *Accepted*, *Pre-arbitration received*, *Arbitration*, or *Arbitration received* |
| Payment Method | Payment method used in the Commerce transaction for an order |
| Website | Website from which the order was placed |
| Store | Store from which the order was placed |
| Store View | Store view from which the order was placed |