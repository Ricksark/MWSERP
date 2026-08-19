# SALES ERP v3.0 – Complete Business Management System

## 📦 DOWNLOAD & INSTALLATION

- **Download the HTML file:**  
  `https://github.com/your-username/sales-erp/raw/main/index.html`  
  *(Replace with your actual GitHub repository URL)*

- **Clone the repository:**  
  ```bash
  git clone https://github.com/your-username/sales-erp.git
  cd sales-erp
  ```

- **Run:** Simply open `index.html` in any modern web browser.  
  No server required – everything runs locally in your browser.


## 📋 APPLICATION DESCRIPTION

Sales ERP is a full-featured, browser-based Enterprise Resource Planning system designed for small to medium businesses. It helps you manage:

- Sales Orders & Invoices
- Purchase Orders
- Product Catalog
- Customer & Supplier Databases
- Company Profile
- Currency & Exchange Rates
- Email Invoicing (via EmailJS)
- Webhook Notifications
- Backup & Restore
- Analytics & Reports

All data is stored locally in your browser's `localStorage`, making it portable and requiring no external database.


## ✨ KEY FEATURES

### 1. DASHBOARD
- Real-time revenue, order, purchase, product, and customer statistics
- Recent sales and purchases overview
- Quick navigation to all sections

### 2. SALES MANAGEMENT
- Create, edit, and delete sales orders
- Auto-generated order numbers (`S-001`, `S-002`, …)
- Status tracking: *Pending, Processing, Completed, Cancelled*
- Add multiple products per order with quantity
- Print professional tax invoices with GST breakdown
- Email invoices directly to customers via EmailJS

### 3. PURCHASE MANAGEMENT
- Create, edit, and delete purchase orders
- Auto-generated PO numbers (`PO-001`, `PO-002`, …)
- Status tracking: *Ordered, Received, Cancelled*
- Add multiple products per purchase

### 4. PRODUCT CATALOG
- Add, edit, and delete products
- Fields: Name, SKU, Price, Stock, Category, HSN Code, Description
- Prices stored in USD and displayed in your chosen currency

### 5. CUSTOMER & SUPPLIER MANAGEMENT
- Full CRUD operations for customers and suppliers
- Fields: Name, Email, Phone, Company, GST, Address

### 6. COMPANY PROFILE
- Configure your business details (used in invoice generation)
- Fields: Company Name, Address, Phone, Email, GST, Website

### 7. SETTINGS
- Currency selection (USD, INR, EUR, GBP, JPY, CAD, AUD)
- Real-time exchange rate fetching
- Google OAuth Client ID configuration
- EmailJS configuration (Public Key, Service ID, Template ID)
- Invoice configuration:
  - CGST & SGST tax rates
  - Invoice terms & conditions
  - Invoice footer note

### 8. INVOICE SYSTEM
- Professional tax invoice generation
- GST breakdown (CGST + SGST)
- Amount in words
- Company details and customer details
- Terms & conditions section
- Print / PDF export
- Email delivery via EmailJS

### 9. WEBHOOK SYSTEM
- Configure webhook endpoints for real-time notifications
- Event types:
  - `sale.created`, `sale.updated`, `sale.deleted`
  - `purchase.created`, `purchase.updated`, `purchase.deleted`
  - `product.created`, `product.updated`, `product.deleted`
  - `customer.created`, `customer.updated`, `customer.deleted`
- Retry mechanism (0–5 attempts)
- Webhook secret for verification
- Activity log with status tracking

### 10. BACKUP & RESTORE
- Download full data backup as JSON
- Upload and restore from backup file
- Data summary view

### 11. MORE SECTION
- Reports: Sales, Purchase, Inventory, Tax reports
- Analytics: Sales by Category, Monthly Revenue, Order Trends
- Export: CSV export for Sales, Purchases, Products, Customers
- Activity Log: Track all user actions


## 🔧 SETUP INSTRUCTIONS

### 1. GOOGLE SIGN-IN (Mandatory)
1. Go to [Google Cloud Console](https://console.cloud.google.com)
2. Create a new project or select existing
3. Enable the **Google+ API**
4. Create OAuth 2.0 Client ID:
   - Application type: **Web application**
   - Authorized JavaScript origins: `http://localhost`, `https://your-domain.com`
   - Authorized redirect URIs: `http://localhost`
5. Copy your **Client ID**
6. Paste it in **Settings → Google Client ID**

### 2. EMAILJS (For Email Invoicing) – Optional
1. Sign up at [EmailJS](https://www.emailjs.com)
2. Create a new email service (Gmail, Outlook, etc.)
3. Create an email template for invoices
4. Copy your:
   - **Public Key** (from Account → API Keys)
   - **Service ID**
   - **Template ID**
5. Paste them in **Settings → EmailJS Configuration**

### 3. WEBHOOKS – Optional
1. Set up a webhook endpoint on your server
2. Enter the URL in the **Webhooks** section
3. Select events to send
4. (Optional) Set a secret for verification
5. Test the webhook using the **“Test Webhook”** button


## 📊 DATA STRUCTURE

All data is stored in `localStorage` under the key:  
`sales_erp_data_v3_{user_email}`

| Collection | Fields |
|------------|--------|
| **products** | `id`, `name`, `sku`, `price`, `stock`, `category`, `description`, `hsn` |
| **sales** | `id`, `orderNumber`, `customerId`, `date`, `items`, `total`, `status` |
| **purchases** | `id`, `poNumber`, `supplierId`, `date`, `items`, `total`, `status` |
| **customers** | `id`, `name`, `email`, `phone`, `company`, `gst`, `address` |
| **suppliers** | `id`, `name`, `email`, `phone`, `company`, `gst`, `address` |
| **company** | `name`, `address`, `phone`, `email`, `gst`, `website` |
| **settings** | `currency`, `useRealTime`, `rates`, `lastUpdate`, `googleClientId`, `emailjsPublic`, `emailjsService`, `emailjsTemplate`, `cgstRate`, `sgstRate`, `invoiceTerms`, `invoiceFooter` |
| **webhook** | `url`, `secret`, `events`, `retries`, `enabled`, `logs` |
| **logs** | Array of `{ time, action, details }` |


## 🖥️ TECHNICAL STACK

- HTML5 / CSS3 / JavaScript (Vanilla, no frameworks)
- Font Awesome 6.5.0 – Icons
- Google Fonts (Inter) – Typography
- Google Identity Services – Mandatory Google Sign-In
- EmailJS – Email delivery for invoices
- ExchangeRate-API – Real-time currency rates
- `localStorage` – Data persistence


## 📱 RESPONSIVE DESIGN

- **Desktop:** Full sidebar navigation, spacious layout
- **Tablet:** Collapsible sidebar, adjusted grid
- **Mobile:** Hamburger menu, stacked layouts, touch-friendly buttons


## 🔐 SECURITY NOTES

- All data is stored locally in your browser (`localStorage`)
- No data is sent to any server except:
  - Google Sign-In authentication (OAuth 2.0)
  - ExchangeRate-API (for currency rates)
  - EmailJS (for sending invoices)
  - Webhook endpoints (configurable)
- Google Sign-In is mandatory – each user has their own data namespace
- Webhook secret is sent as a header for verification


## 📄 LICENSE

This software is provided *"as is"* for educational and demonstration purposes.  
You are free to use, modify, and distribute it for personal or commercial use.



## 📞 SUPPORT

For issues or feature requests, please open an issue on GitHub:  
`https://github.com/your-username/sales-erp/issues`

---

## 📁 FILE STRUCTURE

```
sales-erp/
├── index.html          # Main application (single HTML file)
└── README.txt          # This file
```



## 🚀 QUICK START

1. Open `index.html` in your browser
2. Sign in with Google
3. Configure your **Company Details**
4. Add **Products**, **Customers**, and **Suppliers**
5. Create **Sales** and **Purchase** orders
6. Generate and **email invoices**
7. Set up **Webhooks** for real-time notifications
8. **Backup** your data regularly



*© 2026 Sales ERP v3.0 – Built with ❤️ for small businesses.*
```
