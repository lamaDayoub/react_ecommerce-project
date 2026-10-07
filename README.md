

```markdown
# 🛒 E-Commerce Web Application (React Frontend)

A modern, responsive e-commerce web application built using **React 19**, **React Router v7**, **Vite**, and **Axios**. The frontend interfaces with a REST API backend to deliver a complete online shopping workflow, including product browsing, dynamic search, shopping cart management, checkout summary calculations, and order tracking.

---

## 📁 Repository Structure

```text
react_ecommerce-project/
├── ecommerce-project/       # React 19 Frontend Application
│   ├── src/                 # Application source code (Pages, Components, Assets)
│   ├── package.json         # Project dependencies & scripts
│   └── vite.config.js       # Vite configuration & API proxy setup
└── ecommerce-backend/       # Pre-built Course Backend API

```

> **Note:** The backend service located in `ecommerce-backend/` was provided as part of the course curriculum. The code implemented in `ecommerce-project/` represents the standalone **React frontend client**.

---

## ✨ Features & Functional Highlights

* 🔎 **Product Browsing & Live Search (`HomePage`)**
* Synchronizes with `/api/products` to render product items.
* Implements search filters driven by `useSearchParams` URL query parameters (`/?search=query`).


* 🛍️ **Global Cart State Management (`App.jsx`)**
* Manages cart state centrally using Axios asynchronously fetching `/api/cart-items?expand=product`.
* Live item counter rendered continuously across site headers (`Header` and `CheckoutHeader`).


* 💳 **Checkout & Summary Engine (`CheckoutPage`)**
* Real-time fetching of shipping options (`/api/delivery-options`) and pricing breakdowns (`/api/payment-summary`).
* Item detail updates and instant cost calculations for items, shipping, subtotal, and tax.
* Post-order creation via `POST /api/orders` with direct navigation to order history.


* 🚚 **Order History & Tracking (`OrdersPage`, `TrackingPage`)**
* Overview of past orders with individual tracking views bound to dynamic route parameters (`/tracking/:orderId/:productId`).


* ⚡ **Developer Tooling & Testing**
* Unit and component testing pre-configured using **Vitest**, **React Testing Library**, and `jsdom`.
* Accessible `data-testid` properties across key UI elements.



---

## 🛠️ Tech Stack

| Category | Technology |
| --- | --- |
| **Frontend Framework** | [React 19](https://react.dev/) |
| **Build Tool & Dev Server** | [Vite 6](https://vitejs.dev/) (with `babel-plugin-react-compiler`) |
| **Routing** | [React Router v7](https://reactrouter.com/) |
| **HTTP Client** | [Axios](https://axios-http.com/) |
| **Date Formatting** | [Day.js](https://day.js.org/) |
| **Testing** | [Vitest](https://vitest.dev/) & [React Testing Library](https://testing-library.com/) |
| **Linting & Quality** | [ESLint 9](https://eslint.org/) |

---

## 🚀 Getting Started

### 1. Prerequisites

* **Node.js**: v18.x or higher
* **npm**: v9.x or higher

### 2. Environment Setup & Installation

Clone the repository and install the dependencies for the frontend application:

```cmd
git clone [https://github.com/lamaDayoub/react_ecommerce-project.git](https://github.com/lamaDayoub/react_ecommerce-project.git)
cd react_ecommerce-project/ecommerce-project
npm install

```

### 3. Running the Backend Server

Start the course backend API server so it listens on `http://localhost:3000`:

```cmd
cd ../ecommerce-backend
npm start

```

### 4. Running the React Application

In a separate terminal, navigate to `ecommerce-project` and launch the Vite development server:

```cmd
cd ../ecommerce-project
npm run dev

```

Open your browser and navigate to `http://localhost:5173`.

---

## 🔄 API Proxying Setup

The Vite development server uses local proxying in `vite.config.js` to bypass CORS constraints and route API calls seamlessly to the course backend:

```javascript
// vite.config.js
export default defineConfig({
  plugins: [react(/* ... */)],
  server: {
    proxy: {
      '/api': { target: 'http://localhost:3000' },
      '/images': { target: 'http://localhost:3000' }
    }
  }
})

```

---

## 📜 Available Scripts

Inside the `ecommerce-project` directory, you can run:

| Command | Action |
| --- | --- |
| `npm run dev` | Launches the local development server with Vite |
| `npm run build` | Compiles production-ready build assets |
| `npm run preview` | Previews the production build locally |
| `npm run lint` | Runs ESLint check across all files |
| `npx vitest` | Executes component and unit test suites |

```

---

