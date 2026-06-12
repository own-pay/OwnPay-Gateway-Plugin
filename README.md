# OwnPay Gateway Plugin Suite

<p align="center">
  <strong>Enterprise-ready payment gateway adapters for the OwnPay ecosystem.</strong><br />
  Curated integrations across global, regional, mobile financial services, and crypto payment rails.
</p>

<p align="center">
  <img alt="PHP 8.1+" src="https://img.shields.io/badge/PHP-8.1%2B-777BB4?style=for-the-badge&logo=php&logoColor=white" />
  <img alt="Gateways" src="https://img.shields.io/badge/Gateways-123-0F766E?style=for-the-badge" />
  <img alt="License AGPLv3" src="https://img.shields.io/badge/License-AGPLv3-A50034?style=for-the-badge" />
</p>

---

## Overview

This repository is the official **OwnPay gateway module collection**.  
Each gateway is packaged as a standalone plugin module and includes:

- `manifest.json` (metadata, requirements, CSP, permissions, category)
- `*Gateway.php` (gateway adapter implementation)
- `icon.svg` (provider icon)

The suite currently includes **123 gateway modules** spanning global and local payment methods.

---

## Gateway Coverage

| Category | Count |
|---|---:|
| Global | 70 |
| MFS (Mobile Financial Services) | 30 |
| Bank | 6 |
| Europe | 5 |
| APAC | 2 |
| LATAM | 2 |
| MENA | 2 |
| Mobile | 2 |
| Express | 2 |
| Africa | 1 |
| Crypto | 1 |

### Selected Integrations

Stripe, PayPal Checkout, Adyen, Razorpay, bKash API, Nagad Merchant API, SSLCommerz, Coinbase Commerce, BTCPay, Binance, Square, Flutterwave, Worldpay, and many more.

---

## Module Architecture

Each adapter follows a consistent contract pattern in the OwnPay plugin ecosystem:

- Defines metadata (`name`, `slug`, `version`, `category`, `requires`)
- Declares capabilities (`gateway`, and optional refund support)
- Provides configuration fields for merchant credentials
- Implements transaction lifecycle methods:
  - initiate payment
  - verify callback/webhook
  - process refund (when supported)
- Includes provider-specific CSP and permission declarations

This layout keeps modules isolated, auditable, and easy to maintain.

---

## Requirements

- **PHP:** `>=8.1`
- **OwnPay Core:** `>=0.1.0`

---

## Repository Layout

```text
.
├── LICENSE
├── README.md
├── stripe/
│   ├── manifest.json
│   ├── StripeGateway.php
│   └── icon.svg
├── paypal-checkout/
│   ├── manifest.json
│   ├── PaypalCheckoutGateway.php
│   └── icon.svg
└── ... (123 gateway modules)
```

---

## Security & Compliance Notes

- Server-side verification is expected for gateway callbacks/webhooks.
- Webhook signature validation should be enforced where available.
- CSP and permission boundaries are declared per module via `manifest.json`.

---

## License

This project is licensed under the **GNU Affero General Public License v3.0 (AGPL-3.0)**.  
See [`LICENSE`](./LICENSE) for full terms.

---

## Maintained by

**OwnPay Core Team**  
Official gateway plugin repository for the OwnPay platform.
