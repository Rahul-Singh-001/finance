# finance-dashboard
# 📈 FinTrack - Finance Investment Dashboard

A full-stack investment tracking web application built with React.js, Node.js, Express, and MySQL. Users can track their stock portfolio, monitor profit/loss, view market prices, and manage their investment history.

![FinTrack Dashboard](https://img.shields.io/badge/Status-Live-brightgreen) ![Node](https://img.shields.io/badge/Node.js-v22-green) ![React](https://img.shields.io/badge/React-v18-blue) ![MySQL](https://img.shields.io/badge/MySQL-8.0-orange)

---

## 🚀 Features

- 🔐 **User Authentication** — Register & login with JWT-based security
- 💼 **Portfolio Management** — Add, view, and delete investment holdings
- 📊 **Interactive Charts** — Pie chart for allocation, bar chart for market snapshot
- 💹 **Live Market Prices** — Real-time stock data (mock + Alpha Vantage API ready)
- 📋 **Transaction History** — Track all buy/sell transactions
- 📉 **Profit & Loss Tracking** — Auto-calculated P&L for each holding
- 📱 **Responsive Design** — Works on desktop and mobile

---

## 🛠️ Tech Stack

| Layer | Technology |
|-------|-----------|
| Frontend | React.js, React Router, Recharts, Axios |
| Backend | Node.js, Express.js |
| Database | MySQL, Sequelize ORM |
| Auth | JWT (JSON Web Tokens), bcryptjs |
| Dev Tools | Nodemon, dotenv |

---

## 📁 Project Structure

```
finance-dashboard/
├── backend/
│   ├── config/
│   │   └── database.js         # MySQL + Sequelize setup
│   ├── controllers/
│   │   ├── authController.js   # Register, Login, GetMe
│   │   ├── portfolioController.js
│   │   └── stockController.js
│   ├── middleware/
│   │   └── auth.js             # JWT verification middleware
│   ├── models/
│   │   ├── User.js
│   │   ├── Portfolio.js
│   │   └── Transaction.js
│   ├── routes/
│   │   ├── auth.js
│   │   ├── portfolio.js
│   │   ├── stocks.js
│   │   └── transactions.js
│   ├── .env.example
│   ├── package.json
│   └── server.js
│
└── frontend/
    ├── public/
    │   └── index.html
    └── src/
        ├── components/
        │   ├── Auth/             # Login & Register UI
        │   ├── Dashboard/        # Main dashboard with charts
        │   └── Portfolio/        # Add holding modal
        ├── context/
        │   └── AuthContext.js    # Global auth state
        ├── App.js
        └── index.js
```

---

## ⚙️ Setup & Installation

### Prerequisites
- Node.js v16+
- MySQL 8.0+
- Git

### 1. Clone the Repository
```bash
git clone https://github.com/YOUR_USERNAME/finance-dashboard.git
cd finance-dashboard
```

### 2. Database Setup
```bash
mysql -u root -p
```
```sql
CREATE DATABASE finance_dashboard;
exit;
```

### 3. Backend Setup
```bash
cd backend
npm install
cp .env.example .env
```

Edit `.env` with your credentials:
```env
PORT=5000
DB_HOST=localhost
DB_USER=root
DB_PASSWORD=your_mysql_password
DB_NAME=finance_dashboard
JWT_SECRET=your_secret_key_here
```

Start the backend:
```bash
npm run dev
```
Server runs at `http://localhost:5000`

### 4. Frontend Setup
Open a new terminal:
```bash
cd frontend
npm install
npm start
```
App runs at `http://localhost:3000`

---

## 🔌 API Endpoints

### Auth
| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | `/api/auth/register` | Create new account |
| POST | `/api/auth/login` | Login user |
| GET | `/api/auth/me` | Get logged-in user |

### Portfolio
| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/api/portfolio` | Get all holdings + summary |
| POST | `/api/portfolio/add` | Add new holding |
| DELETE | `/api/portfolio/:id` | Remove a holding |

### Stocks
| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/api/stocks/top` | Get top stocks list |
| GET | `/api/stocks/:symbol` | Get single stock price |

### Transactions
| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/api/transactions` | Get transaction history |

---

## 📸 Screenshots

### Login Page
> Clean login/register UI with tab switching

### Dashboard Overview
> Summary cards showing Total Invested, Current Value, P&L, and Holdings count with interactive pie and bar charts

### Portfolio Tab
> Full holdings table with avg buy price, current price, and profit/loss per stock

### Markets Tab
> Live market prices grid for top stocks

---

## 🔑 Environment Variables

| Variable | Description |
|----------|-------------|
| `PORT` | Backend server port (default: 5000) |
| `DB_HOST` | MySQL host (default: localhost) |
| `DB_USER` | MySQL username |
| `DB_PASSWORD` | MySQL password |
| `DB_NAME` | Database name |
| `JWT_SECRET` | Secret key for JWT tokens |
| `ALPHA_VANTAGE_API_KEY` | (Optional) For real stock prices |

---

## 🌐 Upgrade to Real Stock Prices

Get a free API key from [Alpha Vantage](https://www.alphavantage.co/support/#api-key) and add it to `.env`:
```
ALPHA_VANTAGE_API_KEY=your_key_here
```
The backend will automatically switch from mock data to live prices.

---

## 🤝 Contributing

1. Fork the repository
2. Create a new branch (`git checkout -b feature/your-feature`)
3. Commit your changes (`git commit -m 'Add some feature'`)
4. Push to the branch (`git push origin feature/your-feature`)
5. Open a Pull Request

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

---

## 👨‍💻 Author

**Mukul** — B.Tech Student  
Built as a major project for campus placement preparation.

> *"Finance meets technology — tracking investments made simple."*
