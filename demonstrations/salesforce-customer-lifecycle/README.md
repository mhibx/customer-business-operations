# Salesforce Customer Lifecycle Demonstration

A self-directed Salesforce CRM demonstration for a fictional B2C gaming
and digital top-up business, **GameHub Indonesia**.

> **Project type:** Hands-on demonstration\
> **Environment:** Salesforce Developer Edition / Trailhead Playground\
> **Data:** Dummy records created for testing\
> **Important:** This is not a production implementation and does not
> represent a Salesforce system used by a former employer.

## 1. Objective

Demonstrate how a simple B2C CRM can connect customer records with
purchase history, automatically classify customer lifecycle stage, and
summarize transaction activity in reports and a dashboard.

The project focuses on a small number of features that can be explained
and tested end to end, rather than a large collection of disconnected
tools.

## 2. Business Scenario

GameHub Indonesia sells digital gaming products such as Mobile Legends
and Free Fire top-ups. The demonstration models individual consumers and
their purchases.

The business questions represented are:

-   Is this customer making their first successful purchase or returning
    for another purchase?
-   Can lifecycle stage be updated automatically from transaction data?
-   Can an operator review transaction details and compare transaction
    value by product?

All names, transactions, amounts, and identifiers in this demonstration
are dummy data.

## 3. Implemented Components

### Customer data

-   Uses Salesforce **Person Accounts** to represent individual B2C
    customers.
-   Includes a custom `Customer Lifecycle Stage` field on the Account.
-   Uses fictional customer records such as Budi Santoso, Rina
    Febrianti, and Ardi Pratama.

### Purchase data model

A custom `Purchase` object (`Purchase__c`) stores transaction-level
information and links each purchase to a customer.

Fields used in the demonstration:

  -----------------------------------------------------------------------
  Field                               Purpose
  ----------------------------------- -----------------------------------
  Purchase Number                     Auto-generated record identifier,
                                      e.g. `PUR-000001`

  Customer                            Lookup relationship to the customer
                                      Account

  Product                             Product purchased, such as Mobile
                                      Legends or Free Fire

  Amount                              Transaction amount

  Purchase Date                       Date and time of purchase

  Status                              Transaction state, including
                                      `Success` and `Pending`

  Payment Method                      Payment method, such as QRIS or
                                      Bank Transfer

  Transaction ID                      Dummy transaction reference for
                                      test records
  -----------------------------------------------------------------------

### Record-triggered Flow

Flow name: `Update Customer Lifecycle from Purchase - V1`

The flow is configured to run when a Purchase record is created or
updated, with entry conditions requiring a successful transaction and a
populated customer relationship.

At a high level, the flow:

1.  Retrieves successful purchases for the customer linked to the
    triggering Purchase.
2.  Loops through the returned purchase records and counts them.
3.  Determines whether the count is at least two.
4.  Updates the customer's `Customer Lifecycle Stage`:
    -   Fewer than two successful purchases → `New Customer`
    -   Two or more successful purchases → `Repeat Customer`

The intended business rule is that pending or otherwise non-successful
transactions must not count toward repeat-customer classification.

### Report and dashboard

Report: `GameHub Successful Purchases`

-   Groups purchase records by `Product`.
-   Summarizes `Amount` by product.
-   Displays subtotals and the grand total.

Dashboard: `GameHub Customer & Transaction Overview`

The dashboard contains:

-   A transaction table grouped by product.
-   A metric showing the sum of transaction amounts.
-   A donut chart comparing transaction value by product.

The dashboard screenshot shows the initial four successful purchases for
Budi Santoso:

  Product            Successful purchases   Transaction value
  ---------------- ---------------------- -------------------
  Mobile Legends                        3         IDR 150,000
  Free Fire                             1          IDR 25,000
  **Total**                         **4**     **IDR 175,000**

These figures describe only the initial dummy dataset shown in the
dashboard screenshots. Later lifecycle tests added additional dummy
transactions, so the report/dashboard may show a different total if
refreshed against the updated Playground data.

## 4. Lifecycle Logic

``` text
Purchase created or updated
          |
          v
Status = Success
AND Customer is populated?
          |
          v
Get successful purchases for that customer
          |
          v
Count successful purchases
          |
          v
Is purchase count >= 2?
       /       \
     Yes        No
      |          |
      v          v
Repeat        New
Customer      Customer
```

## 5. Testing and Validation

The following scenarios were exercised in the Salesforce Playground.

  --------------------------------------------------------------------------------------------------------------------
  Test              Setup / action    Observed result     Evidence
  ----------------- ----------------- ------------------- ------------------------------------------------------------
  1\. First         Created Rina      Lifecycle displayed [Purchase
  successful        Febrianti as a    as `New Customer`   record](screenshots/first-successful-purchase-rina.png),
  purchase          Person Account                        [customer
                    and created                           lifecycle](screenshots/lifecycle-new-customer-rina.png)
                    `PUR-000005` with                     
                    status `Success`                      

  2\. Second        Created another   Lifecycle displayed [Repeat-customer
  successful        successful        as                  lifecycle](screenshots/lifecycle-repeat-customer-rina.png)
  purchase          purchase for Rina `Repeat Customer`   
                    (`PUR-000006`)                        

  3\. First         Created a         Lifecycle displayed [Customer
  successful        successful        as `New Customer`   lifecycle](screenshots/lifecycle-new-customer-ardi.png),
  purchase for      purchase for Ardi before the pending  [successful
  another customer  Pratama           test                purchase](screenshots/successful-purchase-ardi.png)
                    (`PUR-000007`)                        

  4\. Pending       Created           Pending record was  [Pending purchase](screenshots/pending-purchase-ardi.png)
  transaction       `PUR-000008` for  created. A          
                    Ardi Pratama with post-creation       
                    status `Pending`  screenshot of       
                                      Ardi's lifecycle    
                                      field was not       
                                      captured, so the    
                                      unchanged lifecycle 
                                      is **not yet        
                                      independently       
                                      evidenced**         
  --------------------------------------------------------------------------------------------------------------------

### What the tests establish

-   The lifecycle field was observed as `New Customer` after a
    customer's first successful purchase.
-   The lifecycle field was observed as `Repeat Customer` after a second
    successful purchase.
-   A pending purchase record can be created for a customer.
-   The pending-transaction exclusion is part of the intended Flow
    logic, but a separate post-pending lifecycle check should be
    captured before claiming that test as fully passed.

## 6. Screenshots

### Dashboard overview

![Salesforce dashboard with transaction table, total amount metric, and
product donut chart](screenshots/dashboard-overview.png)

### Purchase report grouped by product

![Purchase report grouped by product with subtotals and grand
total](screenshots/purchase-report-grouped-by-product.png)

### First successful purchase and New Customer state

![First successful purchase record for Rina
Febrianti](screenshots/first-successful-purchase-rina.png)

![Rina Febrianti's lifecycle stage displayed as New
Customer](screenshots/lifecycle-new-customer-rina.png)

### Repeat Customer state

![Rina Febrianti's lifecycle stage displayed as Repeat Customer after
the second successful
purchase](screenshots/lifecycle-repeat-customer-rina.png)

### Pending transaction test

![Ardi Pratama's lifecycle stage displayed as New Customer before the
pending transaction test](screenshots/lifecycle-new-customer-ardi.png)

![Successful purchase record for Ardi
Pratama](screenshots/successful-purchase-ardi.png)

![Pending purchase record for Ardi
Pratama](screenshots/pending-purchase-ardi.png)

## 7. Design Decisions and Learning

-   **B2C-first data model:** Person Accounts are used because the
    simulated business serves individual consumers rather than only
    business accounts.
-   **Transaction-level records:** Purchase history is stored in a
    custom object instead of relying only on manually maintained
    customer summary fields.
-   **Lifecycle automation:** Lifecycle stage is derived from successful
    purchase count, providing a simple, explainable retention signal.
-   **Summary report requirement:** Grouping the report by Product turns
    it into a summary report and enables the dashboard metric and chart
    configuration used here.
-   **Evidence-based validation:** Screenshots show observed Salesforce
    states. Any test without a captured post-action state is explicitly
    marked as needing further validation.

## 8. Limitations and Next Steps

This is a learning and portfolio demonstration, not a production-ready
CRM. It currently uses a small amount of manually created dummy data and
does not include integrations with a payment gateway, game supplier, or
external messaging platform.

Recommended next steps:

1.  Capture a screenshot of Ardi Pratama's `Customer Lifecycle Stage`
    after the pending transaction to verify it remains `New Customer`.
2.  Confirm the Flow is active and retain a screenshot of the Flow
    configuration.
3.  Add a small number of focused test cases for transaction updates,
    such as a purchase changing from `Pending` to `Success`.
4.  Document the object relationship and Flow configuration in a concise
    diagram or annotated screenshot.

## 9. Repository Structure

``` text
salesforce-customer-lifecycle/
├── README.md
└── screenshots/
    ├── dashboard-overview.png
    ├── purchase-report-grouped-by-product.png
    ├── first-successful-purchase-rina.png
    ├── lifecycle-new-customer-rina.png
    ├── lifecycle-repeat-customer-rina.png
    ├── lifecycle-new-customer-ardi.png
    ├── successful-purchase-ardi.png
    └── pending-purchase-ardi.png
```

------------------------------------------------------------------------

*Created as a self-directed Salesforce portfolio demonstration by
Muhammad Hibatullah Wafi. All records shown are simulated.*
