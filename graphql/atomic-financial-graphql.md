# Atomic Financial GraphQL

Conceptual GraphQL schema for Atomic Financial's payroll connectivity, direct deposit switching, income and employment verification, tax document retrieval, and merchant card-on-file APIs.

## Overview

Atomic's platform connects consumers and their employers or payroll providers through a user-permissioned infrastructure layer. The REST API at `https://api.atomicfi.com` manages access tokens, tasks, companies, deposit accounts, and webhooks. This GraphQL schema provides a conceptual representation of those resources and their relationships.

## Schema Source

- **REST API Reference**: https://docs.atomicfi.com/reference/api
- **Transact SDK Docs**: https://docs.atomicfi.com/reference/transact-sdk
- **Webhooks Docs**: https://docs.atomicfi.com/reference/webhooks
- **Schema File**: atomic-financial-schema.graphql

## Core Domains

### Tasks

The `Task` type is the central coordination unit for every Atomic operation. A task represents an initiated workflow such as switching direct deposit, verifying income, retrieving tax documents, or authenticating with a payroll provider. Tasks carry a `TaskType` (DEPOSIT, VERIFY, IDENTIFY, TAX, AUTH, PAYLINK, MANAGE, SWITCH) and a `TaskStatus` (PENDING, PROCESSING, COMPLETED, FAILED, ABANDONED, EXPIRED).

### Direct Deposit

Direct deposit switching is Atomic's flagship product. The `DirectDeposit`, `DirectDepositDetails`, `DepositAllocation`, and `DepositAccount` types model the full lifecycle of moving a user's paycheck to a new account. Allocations support three distribution modes: fixed dollar amount, percentage, and remainder (everything left over).

### Payroll and Providers

`Payroll`, `PayrollProvider`, `ProviderDetails`, and `ProviderCapability` represent the thousands of payroll systems, employers, and gig platforms Atomic connects to. Each provider carries an auth method (StandardAuth, TrueAuth, or CoAuth) and a list of supported capabilities.

### Employee and Employment

`Employee`, `EmployeeDetails`, and `EmploymentDetails` capture the consumer's identity and employment relationship. Employment status covers active, inactive, terminated, leave-of-absence, part-time, and contractor states.

### Income and Pay Statements

`Income`, `IncomeDetails`, `PayStatement`, `PayStatementDetails`, `Earnings`, `EarningDetails`, `Deductions`, `DeductionDetails`, and `Benefits` model verified payroll-sourced financial data. Pay periods support weekly, biweekly, semimonthly, monthly, daily, and irregular frequencies.

### Tax

`TaxDetails`, `FederalTax`, `StateTax`, `LocalTax`, and `TaxWithholding` represent the tax layer across federal, state, and local jurisdictions. Atomic retrieves W-2 and 1099 documents directly from payroll providers to power refund-advance and tax-filing products.

### Authentication

`Authentication`, `AuthDetails`, `SessionDetails`, and `AccessToken` cover Atomic's three auth modes: StandardAuth (credential and 2FA proxy), TrueAuth (deviceless, fully automated), and CoAuth (assisted authentication for hard-to-reach systems).

### Distribution

`Distribution`, `DistributionDetails`, and `DepositAllocation` model how a paycheck is split across one or more destination accounts using fixed amounts, percentages, or remainder logic.

### Webhooks

`Webhook` and `WebhookEvent` represent Atomic's CloudEvents-based notification system. Supported event types include task-status-updated, task-workflow-finished, payroll-data-fetched, deposit-accounts-synced, employment-updated, income-updated, statements-added, timesheets-added, taxes-added, and linked-account connected/disconnected.

### Access Control

`UserToken`, `PublicKey`, `APIKey`, and `Token` model Atomic's token-based access control system. User tokens are short-lived JWTs issued via the REST API and consumed by the Transact SDK to initialize a session.

### Errors

The `Error` type captures API error responses with a code, human-readable message, optional field pointer, and structured details.

## Type Inventory

| Category | Types |
|---|---|
| Tasks | Task, TaskDetails, TaskStatus (enum), TaskType (enum) |
| Direct Deposit | DirectDeposit, DirectDepositDetails, DepositAllocation, AllocationAmount (enum), DirectDepositUpdate, SwitchDetails |
| Accounts | DepositAccount, AccountDetails, AccountType (enum), AccountNumber, RoutingNumber |
| Payroll | Payroll, PayrollDetails, PayrollProvider, ProviderDetails, ProviderType (enum), ProviderCapability |
| Employee | Employee, EmployeeDetails, EmploymentStatus (enum), EmploymentDetails |
| Income | Income, IncomeDetails, IncomeType (enum), PayPeriod, PayPeriodFrequency (enum) |
| Pay Statements | PayStatement, PayStatementDetails, Earnings, EarningDetails, EarningType (enum) |
| Deductions | Deductions, DeductionDetails, DeductionType (enum), Benefits, BenefitItem |
| Tax | TaxDetails, FederalTax, StateTax, LocalTax, TaxWithholding, TaxFilingStatus (enum) |
| Authentication | Authentication, AuthDetails, AuthMethod (enum), SessionDetails, AccessToken |
| Distribution | Distribution, DistributionDetails, DistributionType (enum) |
| Location | WorkLocation |
| Webhooks | Webhook, WebhookEvent, WebhookEventType (enum) |
| Access Control | UserToken, PublicKey, APIKey, Token |
| Errors | Error |

## Operations

### Queries

- `task(id)` / `tasks(status, type, limit, offset)` — fetch task status and details
- `directDeposit(id)` / `directDeposits(taskId)` — fetch deposit switch records
- `depositAccount(id)` / `depositAccounts(employeeId)` — fetch linked bank accounts
- `payroll(id)` / `payrolls(employeeId, providerId)` — fetch payroll connections
- `payrollProvider(id)` / `payrollProviders(type, search)` — search provider network
- `employee(id)` / `employees(status)` — fetch employee records
- `income(id)` / `incomes(employeeId, type)` — fetch verified income data
- `payStatement(id)` / `payStatements(employeeId, startDate, endDate)` — fetch pay stubs
- `taxDetails(employeeId, year)` / `taxWithholding(employeeId)` — fetch tax data
- `webhook(id)` / `webhooks(isActive)` — manage webhook endpoints
- `webhookEvent(id)` / `webhookEvents(webhookId, type)` — inspect event delivery history
- `apiKey(id)` / `apiKeys(environment, isActive)` — manage API keys
- `userToken(id)` — fetch token metadata

### Mutations

- `createUserToken` — issue a short-lived user token for the Transact SDK
- `createTask` — initiate a deposit, verify, tax, or auth task
- `updateDirectDeposit` — update deposit allocations on a connected payroll account
- `createDepositAccount` / `deleteDepositAccount` — manage destination bank accounts
- `createWebhook` / `updateWebhook` / `deleteWebhook` / `testWebhook` — manage event delivery endpoints
- `createAPIKey` / `revokeAPIKey` — manage API access credentials
- `revokeToken` / `revokeSession` — terminate active sessions

### Subscriptions

- `taskStatusUpdated` — real-time task progress notifications
- `webhookEventReceived` — live webhook event stream
- `depositAccountSynced` — account sync notifications
- `incomeUpdated` / `employmentUpdated` / `payStatementAdded` — continuous-access data change events

## Notes

This is a conceptual schema derived from Atomic's public REST API documentation and SDK reference. Atomic does not currently publish a native GraphQL API. This schema is provided for modeling and integration planning purposes.
