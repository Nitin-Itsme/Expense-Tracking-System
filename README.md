
# 📘 Expense Tracking System

A full-stack Expense Tracker built with **FastAPI** (backend) and **Streamlit** (frontend), designed to help users **log, view, and analyze expenses** by category and month.

---

## 📌 Features

✅ Add and update daily expenses  
✅ Categorize expenses (Food, Rent, Shopping, etc.)  
✅ View analytics by **category** and **month**  
✅ Clean bar charts and tabular summaries  
✅ Modular and extensible codebase  
✅ Logging support for debugging

---

## 🏗️ Project Structure

```
.
├── server.py                # FastAPI backend
├── db_helper.py            # Database functions (MySQL)
├── logging_setup.py        # Logger configuration
├── app.py                  # Streamlit main app
├── add_update.py           # Streamlit tab for adding/updating expenses
├── analytics_by_category.py# Streamlit tab for category-wise analytics
├── analytics_by_months.py  # Streamlit tab for month-wise analytics
├── README.md               # Project documentation
```

---

## 🚀 Getting Started

### 1. 🐍 Clone the Repo & Set Up Environment

```bash
git clone https://github.com/yourusername/expense-tracker.git
cd expense-tracker
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
pip install -r requirements.txt
```

> **Note**: You’ll need to install Python ≥ 3.8

---

### 2. 🛠️ Set Up MySQL Database

```sql
CREATE DATABASE expense_manager;

USE expense_manager;

CREATE TABLE expenses (
  id INT AUTO_INCREMENT PRIMARY KEY,
  expense_date DATE NOT NULL,
  amount DECIMAL(10, 2) NOT NULL,
  category VARCHAR(255),
  notes TEXT
);
```

Update the DB credentials in `db_helper.py` if needed.

---

### 3. 🚀 Start FastAPI Backend

```bash
uvicorn server:app --reload
```



---

### 4. 🎯 Start Streamlit Frontend

```bash
streamlit run app.py
```



---

## ⚙️ API Endpoints (FastAPI)

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET    | `/expenses/{expense_date}` | Fetch expenses for a date |
| POST   | `/expenses/{expense_date}` | Add/update expenses for a date |
| POST   | `/analytics` | Get summary by category for a date range |
| GET    | `/monthly_summary/` | Get total expenses per month |

---

## 🛡️ Tech Stack

- **Frontend**: Streamlit  
- **Backend**: FastAPI  
- **Database**: MySQL  
- **Python Modules**: pandas, requests, logging

---

## 📦 Dependencies

Install dependencies:

```bash
pip install streamlit fastapi uvicorn pandas requests mysql-connector-python
```

---

## 🧩 To-Do (Suggestions)

- [ ] Add user authentication
- [ ] Export analytics to Excel
- [ ] Pagination for long expense lists
- [ ] Dockerize the app
- [ ] Deploy online (e.g. Render, Railway)

---

## 🤝 License

This project is open-source under the [MIT License](LICENSE).
