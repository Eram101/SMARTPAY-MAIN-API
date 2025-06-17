# SmartPay API Documentation

![SmartPay Logo](https://via.placeholder.com/150x50?text=SmartPay)  
**Seamless M-Pesa Integration for Your Applications**

## Table of Contents
- [Introduction](#introduction)
- [Getting Started](#getting-started)
- [API Endpoints](#api-endpoints)
- [Error Codes](#error-codes)
- [Supported Banks](#supported-banks)
- [Best Practices](#best-practices)
- [Contributing](#contributing)
- [License](#license)

## Introduction
SmartPay is a payment service that enables you to collect payments through M-Pesa STK Push directly to your M-Pesa till number, paybill number, or connected bank account. This API provides developers with tools to integrate M-Pesa payments into their applications.

Key Features:
- STK Push payments
- Account balance checking
- Transaction status verification
- Webhook callbacks
- Comprehensive error handling

## Getting Started

### Prerequisites
- SmartPay merchant account
- API key (obtained from your SmartPay dashboard)
- Basic understanding of REST APIs and JSON

### Authentication
All API requests must include your API key in the Authorization header:

```http
Authorization: Bearer your_api_key_here
Sandbox Testing
Use our sandbox environment for testing:

Base URL: https://sandbox.smartpay.co.ke/api/v1

Test phone numbers: 254708374149, 254712345678

API Endpoints
1. Initiate STK Push
Initiate M-Pesa payments via STK Push.

Endpoint: POST /v1/initiatestk

Request Example:

json
{
  "phone": "254712345678",
  "amount": 150,
  "account_reference": "ORDER_101",
  "description": "Payment for services"
}
Response Example:

json
{
  "success": true,
  "message": "STK Push initiated successfully",
  "checkoutRequestID": "ws_CO_16062025160832822727856009",
  "merchantRequestID": "aea5-4f44-b4a1-d9044446ee461957335"
}
2. Check Account Balance
Retrieve your account balance information.

Endpoint: POST /v1/initiatebalance

Request Example:

json
{
  "phone": "254712345678",
  "account_reference": "BALANCE"
}
3. Transaction Status
Check the status of a transaction.

Endpoint: POST /v1/transactionstatus

Request Example:

json
{
  "CheckoutRequestID": "ws_CO_17062025005554749727856009"
}
Error Codes
Code	Description
0	Success
1	Insufficient balance
1032	Request cancelled by user
1037	User cannot be reached (timeout)
2001	Invalid initiator information
Full error code list available in the documentation.

Supported Banks
SmartPay supports integration with over 30 Kenyan banks including:

Equity Bank (247247)

KCB (522522)

Co-operative Bank (400200)

Standard Chartered (329329)

Absa Bank (303030)

View full list of supported banks

Best Practices
Security
Always use HTTPS

Never expose API keys in client-side code

Implement IP whitelisting

Performance
Use webhooks instead of polling

Implement proper error handling

Cache frequently accessed data

Testing
Start with small amounts

Verify callback URL functionality

Test all error scenarios

Contributing
We welcome contributions to the SmartPay API. Please follow these steps:

Fork the repository

Create your feature branch (git checkout -b feature/AmazingFeature)

Commit your changes (git commit -m 'Add some AmazingFeature')

Push to the branch (git push origin feature/AmazingFeature)

Open a Pull Request

License
Distributed under the MIT License. See LICENSE for more information.

Support
For technical support, please contact:

Email: support@smartpay.co.ke

Phone: +254 700 000000

View Full Documentation | Get API Key | GitHub Repository

text

This README includes:

1. **Clear structure** with table of contents
2. **Concise overview** of the API's purpose and features
3. **Getting started** section with prerequisites
4. **API endpoint** documentation with examples
5. **Error code** reference
6. **Best practices** for implementation
7. **Contribution guidelines**
8. **License information**
9. **Support contacts**

The markdown is formatted for easy reading on GitHub and other platforms that support Markdown rendering. You can customize the placeholder logo, support contacts, and other specific details as needed.
