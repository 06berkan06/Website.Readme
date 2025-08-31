# Website.Readme
Bu projedeki kodlar gizli olduğu için sadece içinde nelerden oluştuğu ve ne olduğu yazmaktadır


# Ulusar Web Application

A modern full-stack web application for industrial equipment and machinery solutions, built with FastAPI, PostgreSQL, and React.

## 🚀 Features

- **FastAPI Backend**: High-performance API with automatic documentation
- **PostgreSQL Database**: Robust data storage with SQLAlchemy ORM
- **React Frontend**: Modern UI with TailwindCSS and Framer Motion
- **Admin Panel**: Complete CRUD operations for product management
- **Image Upload**: Support for product images with validation
- **Authentication**: JWT-based authentication system
- **SEO Ready**: Meta tags and structured data
- **Responsive Design**: Mobile-first approach
- **Docker Support**: Easy deployment with Docker Compose

## 🛠️ Tech Stack

### Backend
- **FastAPI**: Modern Python web framework
- **PostgreSQL**: Primary database
- **SQLAlchemy**: ORM for database operations
- **Alembic**: Database migrations
- **Pydantic**: Data validation
- **JWT**: Authentication
- **Pillow**: Image processing

### Frontend
- **React 18**: Modern React with hooks
- **TypeScript**: Type safety
- **TailwindCSS**: Utility-first CSS framework
- **Framer Motion**: Animation library
- **React Query**: Data fetching and caching
- **React Router**: Client-side routing
- **Lucide React**: Icon library

## 📁 Project Structure

```
ulusar-web-app/
├── backend/
│   ├── app/
│   │   ├── api/           # API routes
│   │   ├── core/          # Configuration and utilities
│   │   ├── models/        # Database models
│   │   ├── schemas/       # Pydantic schemas
│   │   └── services/      # Business logic
│   ├── requirements.txt
│   ├── main.py
│   └── seed_data.py       # Database seeding
├── frontend/
│   ├── src/
│   │   ├── components/    # Reusable components
│   │   ├── pages/         # Page components
│   │   ├── services/      # API services
│   │   └── utils/         # Utility functions
│   ├── package.json
│   └── tailwind.config.js
├── docker-compose.yml
└── README.md
```

## 🚀 Quick Start

### Prerequisites
- Docker and Docker Compose
- Node.js 18+ (for local development)
- Python 3.11+ (for local development)

### Using Docker (Recommended)

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd ulusar-web-app
   ```

2. **Start the application**
   ```bash
   docker-compose up -d
   ```

3. **Seed the database**
   ```bash
   docker-compose exec backend python seed_data.py
   ```

4. **Access the application**
   - Frontend: http://localhost:3000
   - Backend API: http://localhost:8000
   - API Documentation: http://localhost:8000/docs

### Local Development

#### Backend Setup

1. **Navigate to backend directory**
   ```bash
   cd backend
   ```

2. **Create virtual environment**
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

4. **Set up PostgreSQL**
   - Install PostgreSQL
   - Create database: `ulusar_db`
   - Update `app/core/config.py` with your database URL

5. **Run migrations**
   ```bash
   alembic upgrade head
   ```

6. **Seed the database**
   ```bash
   python seed_data.py
   ```

7. **Start the server**
   ```bash
   uvicorn main:app --reload
   ```

#### Frontend Setup

1. **Navigate to frontend directory**
   ```bash
   cd frontend
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Start development server**
   ```bash
   npm run dev
   ```

## 🔐 Authentication

### Admin Access
- **Username**: admin
- **Password**: admin123
- **URL**: http://localhost:3000/admin/login

### API Authentication
The API uses JWT tokens for authentication. Include the token in the Authorization header:
```
Authorization: Bearer <your-token>
```

## 📊 API Endpoints

### Authentication
- `POST /auth/login` - User login
- `POST /auth/register` - User registration
- `GET /auth/me` - Get current user

### Products
- `GET /products/` - List products with filtering
- `GET /products/{id}` - Get product by ID
- `GET /products/sku/{sku}` - Get product by SKU
- `POST /products/` - Create product (admin only)
- `PUT /products/{id}` - Update product (admin only)
- `DELETE /products/{id}` - Delete product (admin only)
- `GET /products/categories/list` - List categories
- `GET /products/brands/list` - List brands
- `POST /products/upload-image` - Upload product image (admin only)

## 🎨 Features

### Product Management
- Create, read, update, delete products
- Image upload with validation
- Category and brand filtering
- Search functionality
- Pagination
- Featured products

### User Interface
- Responsive design
- Smooth animations
- Modern UI components
- SEO optimization
- Loading states
- Error handling

### Admin Panel
- Secure authentication
- Product CRUD operations
- Image management
- User management
- Dashboard analytics

## 🔧 Configuration

### Environment Variables

#### Backend
- `DATABASE_URL`: PostgreSQL connection string
- `SECRET_KEY`: JWT secret key
- `ACCESS_TOKEN_EXPIRE_MINUTES`: Token expiration time
- `UPLOAD_DIR`: Directory for uploaded files
- `MAX_FILE_SIZE`: Maximum file size in bytes
- `ALLOWED_EXTENSIONS`: Allowed file extensions

#### Frontend
- `VITE_API_URL`: Backend API URL

## 🐳 Docker Commands

```bash
# Start all services
docker-compose up -d

# Stop all services
docker-compose down

# View logs
docker-compose logs -f

# Rebuild containers
docker-compose up --build

# Access backend container
docker-compose exec backend bash

# Access frontend container
docker-compose exec frontend sh
```

## 📝 Development

### Code Style
- Backend: Black, isort, flake8
- Frontend: ESLint, Prettier

### Database Migrations
```bash
# Create migration
alembic revision --autogenerate -m "Description"

# Apply migrations
alembic upgrade head

# Rollback migration
alembic downgrade -1
```

### Testing
```bash
# Backend tests
pytest

# Frontend tests
npm test
```

## 🚀 Deployment

### Production Setup
1. Update environment variables
2. Set up PostgreSQL database
3. Configure reverse proxy (nginx)
4. Set up SSL certificates
5. Configure domain and DNS

### Environment Variables for Production
```bash
DATABASE_URL=postgresql://user:password@host:port/db
SECRET_KEY=your-secure-secret-key
CORS_ORIGINS=["https://yourdomain.com"]
```

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Add tests if applicable
5. Submit a pull request

## 📄 License

This project is licensed under the MIT License.

## 🆘 Support

For support and questions:
- Create an issue on GitHub
- Contact: info@ulusar.com

## 🔄 Updates

### Version 1.0.0
- Initial release
- Complete CRUD operations
- Admin panel
- Image upload
- Responsive design
- Docker support

