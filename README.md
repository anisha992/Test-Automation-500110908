# FastAPI Test Automation Framework

An efficient FastAPI-based backend designed for automated testing and CI/CD workflows. This project showcases best practices in API development, test automation, and seamless integration with GitHub Actions.

---
## 🚀 Key Highlights

### 🔹 Core API Features
- Arithmetic operations (addition, subtraction, multiplication, square root)
- Secure user authentication (JWT-based)
- Persistent operation history tracking
- Robust input validation
- Centralized error handling
- Structured logging system

### 🧪 Automated Testing Capabilities
- Unit testing via Pytest
- API integration tests
- Performance testing with Locust
- Comprehensive test coverage reports
- Allure & HTML-based test reports

### 🔄 CI/CD Pipeline Integration
- Automated test execution with GitHub Actions
- PostgreSQL container for database testing
- Dynamic environment configurations
- Test artifact storage for debugging

---
## 📌 Setting Up the Project

### 1️⃣ Prerequisites
Ensure you have the following installed:
- Python 3.8+
- PostgreSQL (for production database)
- Git

### 2️⃣ Installation Steps

#### Clone the Repository:
```bash
git clone <repository-url>
cd FastAPI-Test-Framework
```

#### Set Up a Virtual Environment:
```bash
python -m venv venv
source venv/bin/activate  # Windows: venv\Scripts\activate
```

#### Install Dependencies:
```bash
pip install -r requirements.txt
```

---
## ⚙️ Configuration & Setup

### 🔧 Environment Variables
Create a `.env` file and configure the necessary environment settings:
```env
DATABASE_URL=postgresql+asyncpg://postgres:postgres@localhost:5432/arithmetic_db
ENV=development
SECRET_KEY=your-secret-key
ACCESS_TOKEN_EXPIRE_MINUTES=30
```

### 🔄 Database Initialization
```bash
python -c "from database import init_db; import asyncio; asyncio.run(init_db())"
```

---
## ▶️ Running the Application

### Start the FastAPI Server:
```bash
python apiserver.py
```

📍 The API will be accessible at: `http://localhost:8000`

### API Documentation:
- Swagger UI: [http://localhost:8000/docs](http://localhost:8000/docs)
- ReDoc: [http://localhost:8000/redoc](http://localhost:8000/redoc)

---
## ✅ Running Tests

### Execute All Tests with Coverage:
```bash
pytest tests/ -v --cov=apiserver --html=report.html --self-contained-html --alluredir=./allure-results
```

### Load Testing with Locust:
```bash
locust -f performance_tests.py --host=http://localhost:8000
```

---
## 🛠 API Endpoints

### 🔑 Authentication
- `POST /register` → Register a new user
- `POST /token` → Authenticate and obtain an access token

### ➗ Arithmetic Operations
- `POST /calculate/add` → Add two numbers
- `POST /calculate/subtract` → Subtract two numbers
- `POST /calculate/multiply` → Multiply two numbers
- `POST /calculate/sqrt` → Compute square root

### 📜 User History
- `GET /history` → Retrieve user’s operation history

---
## 🏗 Project Structure
```
FastAPI-Test-Framework/
├── .github/workflows/
│   └── ci_tests.yml
├── src/
│   ├── apiserver.py
│   ├── config.py
│   ├── auth.py
│   ├── database.py
│   ├── logger.py
│   ├── models.py
│   ├── routes/
│   │   ├── users.py
│   │   ├── operations.py
├── tests/
│   ├── test_auth.py
│   ├── test_operations.py
│   ├── test_database.py
│   ├── performance_tests.py
├── requirements.txt
├── README.md
```

---
## 🔍 Troubleshooting CI/CD Issues

### 🛑 Common Issues & Fixes

1️⃣ **Invalid Workflow File**
   - **Issue:** "Invalid workflow file: .github/workflows/ci_tests.yml"
   - **Fix:** Corrected YAML syntax by separating commands into distinct steps.

2️⃣ **Missing Dependencies**
   - **Issue:** Test execution failed due to missing imports.
   - **Fix:** Added missing libraries (`httpx`, `starlette`) in `requirements.txt`.

3️⃣ **Artifact Storage Issues**
   - **Issue:** "No files found in ./allure-results"
   - **Fix:** Ensured required directories are created before running tests.

---
## 🔒 Security & Best Practices

- Encrypted JWT authentication
- Secure password hashing using bcrypt
- Input validation using Pydantic
- Environment-based configurations for security

---
## 🤝 Contributing

Interested in contributing? Follow these steps:
1. **Fork** the repository
2. **Create** a new feature branch
3. **Commit** changes with clear messages
4. **Push** to your branch
5. **Submit** a pull request 🚀

---
## 📜 License
This project is licensed under the MIT License.

---
### 🎯 Stay Updated!
For updates and improvements, watch this repository and contribute to its development! 🚀

