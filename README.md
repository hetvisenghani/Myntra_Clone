# E-commerce Clone (Myntra)

A Myntra-style online fashion store built with **React** on the frontend and **Node.js / Express** on the backend. You can browse products by category, see prices and discounts, and add items to your shopping bag.

## Features

- **Home page** shows every product with its image, brand, name, rating, price and discount
- **Category pages** for Men, Women, Kids, Home & Living, Beauty and Studio
- **Shopping bag** where you can add and remove items, with a price summary (total MRP, discount, convenience fee and final amount)
- **Wishlist page** that asks you to log in
- **Login / Signup page** with a mobile number form (only the screen, with no real login behind it)
- **Loading spinner** while products are being fetched from the backend
- **Styled with Bootstrap** and custom CSS

## Tech Stack

| Part | Technologies |
|---|---|
| Frontend | React 18, Vite, React Router, Redux Toolkit, React Redux, Bootstrap 5, React Icons |
| Backend | Node.js, Express, body-parser |
| Data | Product list stored in a JSON file (`myntra-backend/items.json`) |

## How It Works

1. When the app opens, the frontend asks the backend for the product list (`GET /items`).
2. The products are saved in the **Redux store**, so every page can use them.
3. Category pages filter the products by their `category` field (for example `"Men"`).
4. The bag keeps a list of product IDs in Redux. Adding or removing an item updates the bag and its price summary right away.

## Project Structure

```
Myntra-React-Clone-main/
├── myntra-backend/          # Express API
│   ├── index.js             # Server and API routes (port 8081)
│   ├── items.json           # Product data
│   └── data/items.js        # Reads and writes items.json
└── myntra-react/            # React frontend (Vite)
    ├── public/images/       # Product images
    └── src/
        ├── Routes/          # App, Home, Bag and category pages
        ├── components/      # Header, Footer, HomeItem, BagItem, BagSummary, etc.
        └── store/           # Redux slices (items, bag, fetch status)
```

## API Endpoints

| Method | Endpoint | Description |
|---|---|---|
| GET | `/items` | Get all products |
| GET | `/items/:id` | Get one product by ID |
| POST | `/items` | Add a new product |

## Run Locally

**1. Start the backend**

```bash
cd myntra-backend
npm install
npm start
```

The API runs at `http://localhost:8081`.

**2. Start the frontend** (in a second terminal)

```bash
cd myntra-react
npm install
npm run dev
```

Open the address Vite prints, usually `http://localhost:5173`.

> **Note:** The frontend loads products from the URL in `myntra-react/src/components/FetchItem.jsx`. To use your local backend, change that URL to `http://localhost:8081/items`.

## Author

**Hetvi Senghani**
