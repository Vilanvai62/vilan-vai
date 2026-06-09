```
medicare-billing-app/
├── backend/
│   ├── config/
│   │   └── database.js
│   ├── controllers/
│   │   ├── productController.js
│   │   ├── billingController.js
│   │   └── priceController.js
│   ├── routes/
│   │   ├── products.js
│   │   ├── billing.js
│   │   └── prices.js
│   ├── models/
│   │   ├── Product.js
│   │   ├── Billing.js
│   │   └── Price.js
│   ├── middleware/
│   │   └── auth.js
│   ├── server.js
│   ├── package.json
│   └── .env.example
│
├── frontend/
│   ├── public/
│   │   └── index.html
│   ├── src/
│   │   ├── components/
│   │   │   ├── ProductList.jsx
│   │   │   ├── BillingForm.jsx
│   │   │   ├── PriceUpdate.jsx
│   │   │   └── Dashboard.jsx
│   │   ├── pages/
│   │   │   ├── HomePage.jsx
│   │   │   ├── BillingPage.jsx
│   │   │   └── ReportsPage.jsx
│   │   ├── App.jsx
│   │   ├── index.jsx
│   │   └── index.css
│   ├── package.json
│   └── vite.config.js
│
├── database/
│   └── schema.sql
│
├── .gitignore
└── README.md
```
