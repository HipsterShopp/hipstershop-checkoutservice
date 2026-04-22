# Checkout Service

The Checkout Service is a Go microservice that orchestrates the end-to-end order placement workflow for HipsterShop. It acts as the central coordinator, calling downstream services to fetch cart items, price products, convert currencies, process payments, arrange shipping, and send confirmation emails.

## Overview

- **Language:** Go 1.25+
- **Protocol:** HTTP REST
- **Default Port:** `5050`

## API

### `POST /checkout`

Places an order for the given user.

**Request body:**
```json
{
  "userId": "user-123",
  "userCurrency": "USD",
  "address": {
    "streetAddress": "123 Main St",
    "city": "New York",
    "state": "NY",
    "country": "USA",
    "zipCode": 10001
  },
  "email": "user@example.com",
  "creditCard": {
    "creditCardNumber": "4532015112830366",
    "creditCardCvv": 123,
    "creditCardExpirationYear": 2025,
    "creditCardExpirationMonth": 12
  }
}
