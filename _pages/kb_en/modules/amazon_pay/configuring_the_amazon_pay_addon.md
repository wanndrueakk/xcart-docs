---
lang: en
layout: article_with_sidebar
updated_at: '2017-12-04 12:21 +0400'
identifier: ref_0UssH5KP
title: Configuring the Amazon Pay addon
categories:
  - User manual
published: true
order: 130
redirect_from:
  - /modules/pay_with_amazon/configuring_the_pay_with_amazon_module.html
---


After the addon has been {% link "installed and enabled" ref_iCibZ9wD %}, it needs to be configured.

To configure the addon:

1.  In the Installed Addons section of your X-Cart store’s Admin area (**My addons**), locate the entry for the Amazon Pay addon and click the **Settings **link below it:
    ![]({{site.baseurl}}/attachments/7504637/7602403.png)
    The Amazon Pay settings page opens:
    ![]({{site.baseurl}}/attachments/7504637/7602404.png)

2.  Adjust the settings on the page:
    *   **Operation mode**: Use this to switch between the Sandbox and Production modes for the Amazon Payments Advanced integration (_Test_ = Sandbox, _Live_ = Production).
    *   **Amazon Seller ID**: Enter your Merchant ID from your Seller Central account.
    *   **Access Key ID**: Enter your Access Key ID from your Seller Central account.
    *   **Secret Access Key**: Enter your Secret Access Key from your Seller Central account.
    *   **Currency**: Select your currency.
    *   **Capture mode**: Specify the desired capture mode ("Authorization then capture" or "Immediate Charge"). The "Authorization then capture" mode means that, when your buyer submits their order on checkout, you only get an Authorization on the payment method they selected, but not charge the buyer until you fulfill the order. To actually charge the funds you have authorized, you need to manually capture the payment amount by clicking the **Capture** button on the details page of the respective order in your X-Cart store. "Immediate Charge" means that, when buyer submits their order on checkout, the payment is both Authorized and Captured at the same moment.
    *   **Type of authorization request**: Specify the type of authorization request that you would like to be used. This affects the way in which order status will be handled at the time of order placement. 
        With the _Asynchronous_ type of request selected, Amazon will not process authorizations in real time: after an authorization request, your store will receive an immediate API response indicating the Pending status of the authorization, and the order status in your store will become Queued. At this point, the customer will receive an order confirmation with the Queued order status. Later, when the authorization request is processed by Amazon, the store will receive the final processing status of the authorization request (for example, Open or Declined) from Amazon through the Instant Payment Notification service, and the order status in the store will be updated, respectively, to Authorized/Processed (dependes on the Capture mode) or Declined. At this time, the customer will receive another notification - with the updated order status. 
        With the _Synchronous_ type of request selected, it will be different: the authorization request will be either processed or declined by Amazon in real time. In response to your authorization request, Amazon will return either an Open or Declined status in the API response, typically within a few seconds  (If Amazon is unable to process the authorization synchronously, it will return a Declined status). As a result, the order status in your X-Cart store will become either Authorized/Processed (depends on the Capture mode) or Declined right after the order has been placed - while the buyer is still on your store's site. Note that by selecting the _Synchronous_ type of request you may observe a higher authorization decline rate as Amazon will convert some Pending authorizations to Declined. 
3.  Click **Submit** to save the changes.

_Related pages:_

*   {% link "Getting started with Amazon Pay" ref_hU2VNqiL %}