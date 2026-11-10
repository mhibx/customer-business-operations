# Transaction Workflow

This document describes the end-to-end transaction workflow of Insider Top Up, covering customer checkout, payment processing, supplier fulfillment, transaction monitoring, and customer notification.

## 1. Overview

Insider Top Up operates a website-based digital product business where customers can purchase gaming top-up products through an integrated transaction process.

The workflow connects several components:

- Customer-facing website
- Payment gateway (LinkQu)
- Business backend
- Digital product supplier (Digiflazz)
- Customer notification process

Each component supports a different stage of the transaction lifecycle.

## 2. Transaction Flow

### Step 1 — Product Selection and Checkout

Customers visit the Insider Top Up website, select a digital product, provide the required game account information, and proceed to checkout.

Operational considerations:
- Product selection accuracy.
- Correct customer and game account information.
- Order information completeness.
- Transaction record creation.

### Step 2 — Payment Processing

After checkout, the customer selects an available payment method and completes payment through the integrated payment gateway, LinkQu.

The payment gateway processes the payment and provides confirmation to the business system.

Operational considerations:
- Payment status monitoring.
- Payment confirmation.
- Handling delayed payment notifications.
- Matching payment information with the correct order.

### Step 3 — Payment Validation

The business backend receives the payment confirmation and validates the transaction before proceeding with supplier fulfillment.

Operational considerations:
- Confirming successful payment.
- Checking the associated order.
- Preventing fulfillment before payment confirmation.

### Step 4 — Supplier Order Submission

After payment validation, the backend forwards the purchase request to Digiflazz through its API integration.

The supplier receives the request and begins processing the digital product fulfillment.

Operational considerations:
- Correct product and destination information.
- Supplier request submission.
- Supplier transaction reference tracking.
- Monitoring supplier responses.

### Step 5 — Supplier Fulfillment

Digiflazz processes the digital product request and returns a response to the business system.

The response provides information about the supplier-side transaction result.

Possible transaction conditions include:
- Pending
- Processing
- Success
- Failed

### Step 6 — Transaction Status Update

The business backend processes the supplier response and updates the corresponding transaction record.

This allows the business to monitor the transaction lifecycle and identify transactions that require further investigation.

Operational considerations:
- Recording supplier responses.
- Updating transaction status.
- Identifying failed or delayed transactions.
- Maintaining transaction traceability.

### Step 7 — Customer Notification

After the transaction status is updated, the customer receives information about the transaction result.

For transactions requiring further investigation, customer communication and follow-up are handled through customer support channels.

## 3. System Components and Responsibilities

| Component | Responsibility |
|---|---|
| Website | Product selection, checkout, and customer transaction interface |
| LinkQu | Payment processing and payment confirmation |
| Business Backend | Order management, payment validation, supplier request handling, and status updates |
| Digiflazz | Digital product fulfillment and supplier transaction response |
| Customer Support | Customer communication and transaction issue follow-up |

## 4. Transaction Monitoring

Transaction monitoring is important to ensure that customer orders are processed correctly.

Key monitoring activities include:

- Checking payment confirmation.
- Tracking supplier processing status.
- Identifying pending transactions.
- Investigating failed transactions.
- Reviewing supplier response information.
- Following up on unresolved customer issues.

## 5. Exception Handling

Not every transaction follows the normal fulfillment process.

Some transactions may require investigation due to payment delays, supplier processing problems, or incorrect transaction information.

A general issue-handling process includes:

1. Identify the affected order.
2. Review payment and transaction records.
3. Check the supplier response.
4. Determine the stage where the issue occurred.
5. Coordinate with the relevant service provider or supplier.
6. Communicate the progress to the customer.
7. Follow up until the issue is resolved.

## 6. Operational Importance

A structured transaction workflow helps the business maintain:

- Transaction traceability.
- Payment and fulfillment visibility.
- Supplier coordination.
- Faster issue investigation.
- Consistent customer communication.
- Reliable operational records.

## 7. Summary

The Insider Top Up transaction workflow connects customer checkout, payment processing, backend validation, supplier fulfillment, and customer notification.

Understanding this workflow supports effective transaction monitoring, supplier coordination, issue resolution, and overall digital business operations.
