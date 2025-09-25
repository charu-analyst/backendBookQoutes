📚 Book Quote Shorts - Backend API



Notion Press Assessment Project
A powerful REST API for a book quote sharing platform - like "Reels for Books"





🎯 Project Overview

Book Quote Shorts is a modern web application that allows users to discover, share, and interact with inspiring book quotes in a TikTok/Instagram Reels-style format. This backend API provides comprehensive functionality for user management, quote operations, and social interactions.

Built for: Notion Press Technical Assessment
Timeline: 48 hours
Architecture: RESTful API with MongoDB



✨ Key Features

📖 Quote Management





✅ Create, read, update, delete book quotes



✅ Advanced search with filters (author, book title, content)



✅ Category-based organization



✅ Random quote generation for "reels" experience



✅ Trending quotes based on likes



✅ Soft delete functionality

👤 User System





✅ Secure user registration & authentication



✅ JWT-based authorization



✅ Profile management



✅ Password encryption with bcrypt

💝 Social Features





✅ Like/Unlike quotes with atomic operations



✅ Real-time like count tracking



✅ User favorites system



✅ Quote statistics and analytics

🔒 Security & Performance





✅ Input validation with Joi



✅ CORS protection



✅ Environment-based configuration



✅ Error handling middleware



✅ MongoDB atomic operations for data integrity



🏗️ Project Structure

backend/
├── 📄 index.js                    # Application entry point
├── 📁 server/
│   └── 📄 index.js                # Express server configuration
├── 📁 api/
│   ├── 📁 controllers/
│   │   ├── 📄 userController.js   # User authentication & profile
│   │   └── 📄 bookQoutesController.js # Quote management
│   ├── 📁 services/
│   │   ├── 📄 userServices.js     # User database operations
│   │   └── 📄 bookQoutesServices.js # Quote database operations
│   ├── 📁 models/
│   │   ├── 📄 userModel.js        # User schema
│   │   └── 📄 bookQoutesModel.js  # Quote schema
│   └── 📁 routes/
│       └── 📄 bookQoutesRoute.js  # API route definitions
├── 📁 assets/
│   └── 📄 responseMessages.js     # Standardized API responses
├── 📁 node_modules/               # Dependencies
├── 📄 package.json               # Project configuration
└── 📄 .env                       # Environment variables




🚀 Quick Start

Prerequisites





Node.js 18+



MongoDB 5.0+



npm or yarn

Installation





Clone the repository

git clone <repository-url>
cd backend




Install dependencies

npm install




Environment Setup Create a .env file:

PORT=8000
MONGODB_URI=mongodb://localhost:27017/bookquotes
JWT_SECRET=your-super-secure-jwt-secret-key-here
JWT_EXPIRES_IN=7d
NODE_ENV=development




Start the server

npm start




Verify installation

curl http://localhost:5000/api/health




📋 API Documentation

Base URL

http://localhost:5000/api||https://backendbookqoutes.onrender.com


Authentication

All protected routes require JWT token in header:

Authorization: Bearer <jwt-token>




🔐 Authentication Endpoints

Register User

POST /api/auth/register
Content-Type: application/json

{
  "name": "CharuYadav",
  "email": "charu@example.com",
  "password": "securePassword123"
}


Login User

POST /api/auth/login
Content-Type: application/json

{
  "email": "john@example.com",
  "password": "securePassword123"
}


Get User Profile

GET /api/user/profile
Authorization: Bearer <token>




📚 Quote Management Endpoints

Get All Quotes

GET /api/quotes?category=motivation&search=success&sortBy=likeCount&sortOrder=desc


Get Random Quotes (For Reels)

GET /api/quotes/random?count=10&category=inspiration


Get Trending Quotes

GET /api/quotes/trending?limit=20&timeframe=week


Create New Quote

POST /api/quotes
Authorization: Bearer <token>
Content-Type: application/json

{
  "text": "The only way to do great work is to love what you do.",
  "author": "Steve Jobs",
  "bookTitle": "Steve Jobs Biography",
  "category": "motivation",
  "tags": ["work", "passion", "success"]
}






❤️ Social Interaction Endpoints

Search Quote

GET /api/quotes/quotesList

Like Quote

POST /api/quotes/:id/like


Unlike Quote

POST /api/quotes/:id/unlike






🗃️ Database Schema

User Model

{
  _id: ObjectId,
  name: String (required),
  email: String (required, unique),
  password: String (hashed),
  isActive: Boolean (default: true),
  createdAt: Date,
  updatedAt: Date
}


Quote Model

{
  _id: ObjectId,
  text: String (required),
  author: String (required),
  bookTitle: String (required),
  category: String,
  tags: [String],
  likeCount: Number (default: 0),
  isActive: Boolean (default: true),
  createdBy: ObjectId (ref: User),
  createdAt: Date,
  updatedAt: Date
}




🛠️ Technologies Used







Technology



Version



Purpose





Node.js



18+



Runtime environment





Express.js



5.1.0



Web framework





MongoDB



8.18.2



Database





Mongoose



8.18.2



ODM for MongoDB





JWT



9.0.2



Authentication





Bcrypt



6.0.0



Password hashing





Joi



18.0.1



Input validation





CORS



2.8.5



Cross-origin requests





Dotenv



17.2.2



Environment management



🔧 Development Features

Error Handling





Global error middleware



Standardized error responses



Comprehensive logging

Security





JWT token-based authentication



Password hashing with bcrypt



Input validation with Joi



CORS protection



Environment-based configuration

Performance





MongoDB atomic operations



Lean queries for better performance



Soft delete for data integrity



Indexed database fields



🧪 API Response Format

Success Response

{
  "statusCode": "200",
  "responseMessages": "Operation successful",
  "data": { ... },
  "total": 150
}


Error Response

{
  "statusCode": "400",
  "responseMessages": "Validation error",
  "error": "Detailed error message"
}




🚀 Deployment

Environment Variables

NODE_ENV=production
PORT=8000
MONGODB_URI=mongodb+srv://charu:charu@cluster.mongodb.net/bookquotes
JWT_SECRET=jwt-secret


Production Start

npm start




🏆 Assessment Requirements ✅

Core Features Implemented





✅ Display short quotes/snippets from books



✅ Navigation through quotes (API supports filtering)



✅ Quote text, author name, and book title



✅ Smooth data transitions via API

Bonus Features Implemented





✅ Like button functionality



✅ Share functionality (API ready)



✅ Responsive API design



✅ Clean, structured, scalable code

Technical Excellence





✅ Clean folder structure



✅ Comprehensive README



✅ Production-ready code



✅ Scalable architecture



✅ Professional documentation



👨‍💻 Developer Information

Author: CharuLata Yadav
Project: Notion Press Technical Assessment
Contact: [charuyadav594@gmail.com]
GitHub: [(https://github.com/charu-analyst)]
Live Demo: [Deployment URL]



📝 License

ISC License - Charu's Open source project for assessment purposes.



🤝 Contributing

This project was built as a technical assessment for Notion Press. For questions or clarifications, please contact the development team.





Notion Press Assessment - Demonstrating full-stack development capabilities with modern technologies and best practices. Built with ❤️ for the Book Quote Shorts platform.
