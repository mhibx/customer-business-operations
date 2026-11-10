
# Issue and Refund Management

## Overview

This document describes the operational approach used to investigate and resolve transaction issues in Insider Top Up, a digital gaming top-up business.

Transaction issues may occur during order placement, payment processing, supplier fulfillment, or communication between integrated systems.

Effective issue handling requires transaction monitoring, payment verification, supplier coordination, accurate status tracking, and clear customer communication.

## Common Transaction Issues

Operational issues can be grouped into three main categories:

### 1. Order and Product Issues

Issues related to the order details or product selected by the customer.

Examples include:

- Incorrect product or denomination selected.
- Incorrect order details submitted.
- Customer reports an issue with the purchased item.

### 2. Supplier Fulfillment Issues

Issues occurring during digital product fulfillment by the supplier.

Examples include:

- Supplier service disruption.
- Pending or delayed fulfillment.
- Failed supplier transactions.
- Supplier response or status not received as expected.

### 3. Payment Processing Issues

Issues involving payment verification or synchronization between the payment gateway and Insider Top Up.

Examples include:

- Payment has been made, but the payment gateway status has not been updated.
- Payment status is successful in the payment gateway, but the Insider Top Up transaction has not been updated.
- Delayed or unsuccessful webhook communication.
- Payment status requires manual verification before the transaction can proceed.

These issues may require checking both the payment gateway and the business backend to identify where the status synchronization problem occurred.

## Issue Investigation Workflow

### 1. Identify the Issue

Issues can be identified through transaction monitoring, customer inquiries, or internal operational checks.

Relevant information is collected to identify the affected transaction, including:

- Transaction ID
- Customer information
- Product and denomination
- Payment status
- Supplier order status
- Transaction timestamp

### 2. Verify Transaction Status

The transaction is reviewed across the relevant operational components:

- **Insider Top Up:** Review the order record, payment status, and transaction status.
- **LinkQu:** Check the payment status when payment verification is required.
- **Digiflazz:** Review supplier order status and fulfillment results.

For payment-related issues, the status in LinkQu is compared with the transaction status in Insider Top Up.

This helps determine whether the issue is related to payment processing, status synchronization, or the business backend.

### 3. Manual Payment Verification

When payment status is not automatically updated, manual verification may be required.

The general process includes:

1. Identify the affected transaction.
2. Check the payment information and transaction reference.
3. Verify whether the payment has actually been received through the available payment records.
4. Compare the payment gateway status with the Insider Top Up transaction status.
5. Once payment is confirmed, update the transaction through the business system so the order can proceed.

Manual verification helps prevent unpaid transactions from being incorrectly processed while ensuring that legitimate payments are not left unresolved.

### 4. Coordinate with the Supplier

When an issue is related to product fulfillment, supplier status and transaction information are reviewed.

Further coordination or follow-up may be required to clarify pending or failed orders and determine the appropriate next action.

### 5. Communicate with the Customer

Customers receive relevant updates about their transaction.

Communication focuses on:

- Acknowledging the reported issue.
- Explaining the current transaction status.
- Providing updates when further investigation is required.
- Communicating the resolution once the issue is settled.

## Refund Management

Refund handling is part of the transaction resolution process, particularly when an order cannot be fulfilled successfully or requires cancellation.

The general process includes:

1. Review the transaction and confirm its status.
2. Check payment and supplier fulfillment information.
3. Determine whether the transaction requires a refund or another resolution.
4. Process or coordinate the appropriate refund action.
5. Update the transaction record.
6. Inform the customer about the resolution.

Refund-related information is useful for operational tracking, including:

- Transaction ID
- Refund reason
- Refund status
- Refund date
- Related customer communication

## Transaction Monitoring and Records

Transaction records support issue investigation and operational follow-up.

Relevant information can be tracked using the business backend and supporting operational records, including Google Sheets.

Important monitoring points include:

- Pending and delayed transactions.
- Failed supplier fulfillment.
- Payment status discrepancies.
- Transactions requiring manual payment verification.
- Refund cases.
- Repeated transaction issues.
- Resolution status.

These records help maintain visibility into unresolved cases and provide a reference for future investigations.

## Tools and Systems

| Tool / System | Operational Purpose |
|---|---|
| Insider Top Up | Review orders and transaction records |
| LinkQu | Payment processing and payment status verification |
| Digiflazz API | Supplier order processing and fulfillment status |
| Google Sheets | Supporting operational records and tracking |
| WhatsApp Business | Customer communication and issue follow-up |
| Telegram | Operational notifications and coordination |

## Operational Capabilities Demonstrated

This experience demonstrates practical capabilities in:

- Transaction investigation and status verification.
- Payment reconciliation and manual verification.
- Identifying payment status synchronization issues.
- Supplier fulfillment coordination.
- Customer complaint handling.
- Refund case coordination and follow-up.
- Operational record keeping.
- Cross-system issue investigation.
- Clear communication during transaction disruptions.

## Relevance to Merchant Operations

The experience is relevant to merchant and marketplace operations because it involves resolving operational issues across multiple parties and systems.

Similar capabilities are useful when supporting merchants with order issues, payment discrepancies, product fulfillment problems, customer complaints, and refund-related inquiries.

## Scope and Context

This document describes operational experience from managing Insider Top Up, a digital gaming top-up business.

It does not represent experience administering a third-party marketplace's internal payment or refund system, nor does it claim formal ownership of payment gateway infrastructure.

The examples are based on business operations, payment verification, supplier coordination, and customer support activities.
