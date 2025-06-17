SmartPay API Documentation



A comprehensive documentation for the SmartPay API that enables M-Pesa STK Push payments integration in your applications.

Features

STK Push Integration - Initiate M-Pesa payments via push notifications

Transaction Status - Check the status of initiated transactions

Account Balance - Retrieve account information including current balance

Webhook Support - Configure callback URLs for real-time payment notifications

Error Handling - Detailed error codes and descriptions

Supported Banks - List of all supported banks and paybill numbers

API Endpoints

Endpoint

Method

Description

/v1/initiatestk

POST

Initiate STK Push payment

/v1/initiatebalance

POST

Check account balance and info

/v1/transactionstatus

POST

Check transaction status

Getting Started

Prerequisites

PHP 7.2 or higher

MySQL database

Web server (Apache/Nginx)

SmartPay API credentials

Installation

Clone the repository:

git clone https://github.com/ERAM101/SMARTPAY-MAIN-API.git

Configure the database:

Import the SQL schema from database.sql

Update database credentials in server.php

Set up API configuration:

Update API credentials in secure_config.php

Deploy to your web server

Authentication

All API requests require authentication via API key in the Authorization header:

Authorization: Bearer your_api_key_here

Usage Examples

Initiate STK Push

POST /v1/initiatestk HTTP/1.1
Host: api.smartpay.co.ke
Content-Type: application/json
Authorization: Bearer your_api_key_here

{
  "phone": "254712345678",
  "amount": 150,
  "account_reference": "NETON_101",
  "description": "Payment for SmartPlan"
}

Check Account Balance

POST /v1/initiatebalance HTTP/1.1
Host: api.smartpay.co.ke
Content-Type: application/json
Authorization: Bearer your_api_key_here

{
  "phone": "254712345678",
  "account_reference": "BALANCE"
}

Check Transaction Status

POST /v1/transactionstatus HTTP/1.1
Host: api.smartpay.co.ke
Content-Type: application/json
Authorization: Bearer your_api_key_here

{
  "CheckoutRequestID": "ws_CO_17062025005554749727856009"
}

Response Codes

Code

Description

0

Success

1

Insufficient balance

1032

Request cancelled by user

1037

User cannot be reached

1025

Push request error

9999

General error

2001

Invalid initiator info

1019

Transaction expired

1001

Transaction in progress

Supported Banks

SmartPay supports integration with all major Kenyan banks including:

Equity Bank (247247)

KCB (522522/522533)

Co-operative Bank (400200/400222)

Standard Chartered (329329)

And many more (see full list in documentation)

Contributing

Contributions are welcome! Please follow these steps:

Fork the repository

Create your feature branch (git checkout -b feature/AmazingFeature)

Commit your changes (git commit -m 'Add some AmazingFeature')

Push to the branch (git push origin feature/AmazingFeature)

Open a Pull Request

License

Distributed under the MIT License. See LICENSE for more information.

Contact

For support or inquiries:

Email: support@smartpay.co.ke

Phone: +254 700 000000

Website: https://smartpay.co.ke

Acknowledgments

M-Pesa API Documentation

Highlight.js for code syntax highlighting

Inter Font for typography

