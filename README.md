# Medicare Billing App

একটি সম্পূর্ণ অনলাইন মেডিকেয়ার বিলিং সিস্টেম যা প্রোডাক্ট, MRP, DP এবং কারেন্ট প্রাইস ম্যানেজমেন্ট করে।

## 🎯 ফিচা��

- ✅ **প্রোডাক্ট ম্যানেজমেন্ট** - প্রোডাক্ট যোগ, এডিট, ডিলিট করুন
- ✅ **MRP, DP এবং কারেন্ট প্রাইস** - সব ধরনের প্রাইস ট্র্যাক করুন
- ✅ **প্রাইস আপডেট সিস্টেম** - প্রাইস হিস্টরি সহ রিয়েল-টাইম আপডেট
- ✅ **বিলিং সিস্টেম** - সম্পূর্ণ বিলিং ফাংশনালিটি
- ✅ **ট্যাক্স ক্যালকুলেশন** - স্বয়ংক্রিয় ট্যাক্স (18% GST)
- ✅ **ডিসকাউন্ট সিস্টেম** - সহজ ডিসকাউন্ট ম্যানেজমেন্ট
- ✅ **প্রিন্ট ফিচার** - বিল প্রিন্ট করুন

## 🛠️ প্রযুক্তি স্ট্যাক

### Backend
- **Node.js** - রানটাইম এনভায়রনমেন্ট
- **Express.js** - ওয়েব ফ্রেমওয়ার্ক
- **PostgreSQL** - ডেটাবেস
- **JWT** - অথেন্টিকেশন

### Frontend
- **React** - UI ফ্রেমওয়ার্ক
- **Axios** - HTTP ক্লায়েন্ট
- **Vite** - বিল্ড টুল
- **CSS3** - স্টাইলিং

## 📁 প্রজেক্ট স্ট্রাকচার

```
medicare-billing-app/
├── backend/
│   ├── config/          # ডেটাবেস কনফিগ
│   ├── controllers/      # বিজনেস লজিক
│   ├── routes/          # API রুটস
│   ├── middleware/       # মিডলওয়্যার
│   ├── server.js        # মেইন সার্ভার
│   └── package.json
│
├── frontend/
│   ├── src/
│   │   ├── components/   # React কম্পোনেন্টস
│   │   ├── App.jsx
│   │   └── index.jsx
│   ├── public/
│   └── package.json
│
├── database/
│   └── schema.sql       # ডেটাবেস স্কিমা
│
└── README.md
```

## 🚀 শুরু করুন

### প্রিরিকোয়িজিট
- Node.js (v14+)
- PostgreSQL (v12+)
- npm বা yarn

### Backend সেটআপ

```bash
# backend ডিরেক্টরিতে যান
cd backend

# প্যাকেজ ইনস্টল করুন
npm install

# .env ফাইল তৈরি করুন
cp .env.example .env

# .env ফাইল এডিট করুন এবং ডেটাবেস ক্রেডেনশিয়াল যোগ করুন

# ডেটাবেস তৈরি করুন
createdb medicare_billing

# স্কিমা চালান
psql -U postgres -d medicare_billing -f ../database/schema.sql

# সার্ভার চালান
npm run dev
```

সার্ভার `http://localhost:5000` এ চলবে।

### Frontend সেটআপ

```bash
# frontend ডিরেক্টরিতে যান
cd frontend

# প্যাকেজ ইনস্টল করুন
npm install

# ডেভেলপমেন্ট সার্ভার চালান
npm run dev
```

ফ্রন্টএন্ড `http://localhost:3000` এ চলবে।

## 📊 ডেটাবেস স্কিমা

### Products Table
- `id` - প্রাইমারি কী
- `product_name` - প্রোডাক্ট নাম
- `mrp` - Maximum Retail Price
- `dp` - Distributor Price
- `current_price` - কারেন্ট বিক্রয় মূল্য
- `category` - প্রোডাক্ট ক্যাটেগরি
- `stock_quantity` - স্টক পরিমাণ

### Billings Table
- `id` - প্রাইমারি কী
- `bill_number` - ইউনিক বিল নম্বর
- `customer_name` - গ্রাহক নাম
- `customer_phone` - গ্রাহক ফোন
- `total_amount` - মোট পরিমাণ
- `tax_amount` - ট্যাক্স পরিমাণ
- `discount_amount` - ডিসকাউন্ট
- `grand_total` - চূড়ান্ত মোট

### Price History Table
- প্রতিটি প্রাইস পরিবর্তন ট্র্যাক করে

## 🔌 API এন্ডপয়েন্টস

### Products
- `GET /api/products` - সব প্রোডাক্ট পান
- `GET /api/products/:id` - একটি প্রোডাক্ট পান
- `POST /api/products` - নতুন প্রোডাক্ট তৈরি করুন
- `PUT /api/products/:id` - প্রোডাক্ট আপডেট করুন
- `DELETE /api/products/:id` - প্রোডাক্ট ডিলিট করুন

### Billing
- `POST /api/billing` - নতুন বিল তৈরি করুন
- `GET /api/billing` - সব বিল পান
- `GET /api/billing/:id` - একটি বিল এবং আইটেম পান

### Prices
- `GET /api/prices/:productId` - প্রাইস হিস্টরি পান
- `PUT /api/prices/:productId` - প্রাইস আপডেট করুন

## 📱 ব্যবহার

### প্রোডাক্ট যোগ করুন
1. "প্রোডাক্ট" ট্যাবে যান
2. প্রোডাক্ট বিবরণ পূরণ করুন
3. "যোগ করুন" বাটনে ক্লিক করুন

### বিল তৈরি করুন
1. "বিলিং" ট্যাবে যান
2. গ্রাহক তথ্য প্রবেশ করুন
3. প্রোডাক্ট নির্বাচন করুন
4. "বিল তৈরি করুন" ক্লিক করুন

### প্রাইস আপডেট করুন
1. "প্রাইস আপডেট" ট্যাবে যান
2. প্রোডাক্ট নির্বাচন করুন
3. নতুন প্রাইস এবং কারণ প্রবেশ করুন
4. "আপডেট করুন" ক্লিক করুন

## 📝 লাইসেন্স

MIT

## 👨‍💻 অবদানকারী

Vilanvai62

---

**হ্যাপি কোডিং! 🎉**
