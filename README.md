# 📚 Online_books_review_system

Welcome to the **Online Book Review Server-Side Application**, the final project for the IBM Course "**Developing Back-End Apps with Node.js and Express**". This project is designed to provide a platform for managing books, writing reviews, and interacting with book-related data through a RESTful API. The system uses **Node.js** and **Express.js** for server-side logic, **MySQL** as the database, and **Sequelize.js** for ORM (Object-Relational Mapping).

## Project Overview


A comprehensive RESTful API for managing books, users, and reviews built with Node.js, Express.js, and MySQL. This application serves as the backend for an online book review platform where users can discover books, write reviews, and share their reading experiences.

## 🚀 Features

### 🔐 Authentication & Authorization
- User registration and login
- JWT-based authentication
- Secure password hashing with bcrypt
- Protected routes for authenticated users

### 📖 Book Management
- Browse all available books
- Search books by ISBN, title, or author
- Add new books to the collection
- Comprehensive book information storage

### ⭐ Review System
- Write and edit book reviews
- Delete your own reviews
- View all reviews for specific books
- User-specific review management

## 🛠️ Technologies Used

- **Backend**: Node.js, Express.js
- **Database**: MySQL
- **ORM**: Sequelize
- **Authentication**: JSON Web Tokens (JWT)
- **Security**: bcrypt for password hashing
- **Environment**: dotenv for configuration
- **CORS**: Cross-Origin Resource Sharing enabled

## 📋 Prerequisites

Before running this application, make sure you have the following installed:

- [Node.js](https://nodejs.org/) (v14 or higher)
- [MySQL](https://www.mysql.com/) (v8.0 or higher)
- [npm](https://www.npmjs.com/) or [yarn](https://yarnpkg.com/)

## ⚙️ Installation & Setup

1. **Clone the repository**
   ```bash
   git clone https://github.com/yourusername/online-books-review-system.git
   cd online-books-review-system
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Environment Configuration**
   
   Create a `.env` file in the root directory and configure the following variables:
   ```env
   PORT=3000
   DATABASE_NAME=your_database_name
   DATABASE_USERNAME=your_mysql_username
   DATABASE_PASSWORD=your_mysql_password
   DATABASE_HOST=localhost
   SALT_ROUNDS=10
   TOKEN_SECRET_KEY=your_jwt_secret_key
   ```

4. **Database Setup**
   
   Create a MySQL database with the name specified in your `.env` file:
   ```sql
   CREATE DATABASE your_database_name;
   ```

5. **Start the application**
   ```bash
   npm start
   ```

   The server will start running on `http://localhost:3000` (or your specified PORT).

## 🔌 API Endpoints

### Authentication Routes
| Method | Endpoint | Description | Auth Required |
|--------|----------|-------------|---------------|
| POST | `/api/v1/auth/register` | Register a new user | ❌ |
| POST | `/api/v1/auth/login` | Login user | ❌ |

### Book Routes
| Method | Endpoint | Description | Auth Required |
|--------|----------|-------------|---------------|
| GET | `/api/v1/books` | Get all books | ❌ |
| POST | `/api/v1/books` | Add a new book | ❌ |
| POST | `/api/v1/books/byISBN` | Search books by ISBN | ❌ |
| POST | `/api/v1/books/byTitle` | Search books by title | ❌ |
| POST | `/api/v1/books/byAuthor` | Search books by author | ❌ |

### Review Routes
| Method | Endpoint | Description | Auth Required |
|--------|----------|-------------|---------------|
| GET | `/api/v1/books/:id/reviews` | Get reviews for a book | ❌ |
| PUT | `/api/v1/books/:id/reviews` | Add/update review | ✅ |
| DELETE | `/api/v1/books/:id/reviews` | Delete review | ✅ |

## 📁 Project Structure

```
├── app.js                 # Main application file
├── package.json           # Project dependencies and scripts
├── .env                   # Environment variables (not tracked)
├── .gitignore            # Git ignore file
├── config/
│   └── connection.js     # Database configuration
├── controllers/
│   ├── auth.js           # Authentication logic
│   ├── book.js           # Book management logic
│   └── review.js         # Review management logic
├── middleware/
│   ├── authenticate.js   # JWT authentication middleware
│   └── not-found.js      # 404 error handler
├── models/
│   ├── user.js           # User model
│   ├── book.js           # Book model
│   └── review.js         # Review model
├── routes/
│   ├── auth.js           # Authentication routes
│   ├── book.js           # Book routes
│   └── review.js         # Review routes
└── utils/
    ├── hashing.js        # Password hashing utilities
    └── tokens.js         # JWT token utilities
```

## 🔧 Usage Examples

### Register a new user
```bash
curl -X POST http://localhost:3000/api/v1/auth/register \
  -H "Content-Type: application/json" \
  -d '{"username": "johndoe", "password": "securepassword"}'
```

### Login
```bash
curl -X POST http://localhost:3000/api/v1/auth/login \
  -H "Content-Type: application/json" \
  -d '{"username": "johndoe", "password": "securepassword"}'
```

### Add a book review (requires authentication)
```bash
curl -X PUT http://localhost:3000/api/v1/books/1/reviews \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer YOUR_JWT_TOKEN" \
  -d '{"review_text": "This is an amazing book!"}'
```

## 🚦 Development

### Running in Development Mode
```bash
npm start
```

The application uses `nodemon` for automatic restarts during development.

### Database Models

- **User**: Stores user credentials and information
- **Book**: Contains book details (ISBN, title, author)
- **Review**: Junction table linking users and books with review text

## 🤝 Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📝 License

This project is licensed under the ISC License - see the [LICENSE](LICENSE) file for details.

## 📞 Contact

For any questions or suggestions, please feel free to reach out:

- Email: ayushwork981@gmail.com
- GitHub: [@aayushthakur001](https://github.com/aayushthakur001)

## 🙏 Acknowledgments

- Built as part of the IBM Course "Developing back-end apps with Node.js and Express"
- Thanks to all contributors and the open-source community

---

⭐ **If you found this project helpful, please give it a star!** ⭐
