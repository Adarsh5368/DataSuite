# AIS Forecasting System

A comprehensive maritime intelligence and forecasting system that provides real-time ship tracking, traffic analysis, and risk assessment capabilities. This full-stack application combines advanced data analytics with intuitive visualization tools for maritime domain awareness.

AIS Dashboard

## 🚢 Features

### Core Functionality
- **Real-time Ship Tracking**: Live AIS (Automatic Identification System) data visualization
- **Traffic Forecasting**: Predictive analytics for maritime traffic patterns
- **Risk Assessment**: AI-powered risk analysis for ship operations
- **Route Analysis**: Comprehensive route planning and optimization
- **Trends Dashboard**: Historical data analysis and trend visualization
- **Ship Profiles**: Detailed vessel information and operational history

### Technical Features
- **Interactive Maps**: Leaflet-based mapping with ship positions and trajectories
- **Advanced Charts**: Chart.js integration for data visualization
- **Real-time Updates**: Live data streaming and updates
- **User Authentication**: Secure JWT-based authentication system
- **RESTful API**: Comprehensive backend API for data access
- **Responsive Design**: Mobile-friendly Tailwind CSS styling

## 🏗️ Architecture

```
├── Frontend/                 # React + Vite frontend application
│   ├── src/
│   │   ├── components/      # Reusable React components
│   │   ├── services/        # API service layers
│   │   ├── styles/         # CSS and styling
│   │   └── utils/          # Utility functions
├── backend/                 # Flask Python backend API
│   ├── routes/             # API route handlers
│   ├── utils/              # Backend utilities
│   ├── models.py           # Database models
│   └── app.py              # Main application entry
├── ships_with_dynamics_heading.csv  # Core ship data
├── docker-compose.yml       # Container orchestration
└── nginx.conf              # Reverse proxy configuration
```

## 🛠️ Technology Stack

### Frontend
- **React 18** - Modern UI framework
- **Vite** - Fast build tool and dev server
- **Tailwind CSS** - Utility-first CSS framework
- **Leaflet** - Interactive mapping library
- **Chart.js** - Data visualization
- **Axios** - HTTP client for API communication

### Backend
- **Flask** - Python web framework
- **SQLAlchemy** - Database ORM
- **PostgreSQL** - Primary database
- **Flask-JWT-Extended** - Authentication
- **Pandas** - Data manipulation
- **StatsModels** - Statistical analysis

### Infrastructure
- **Docker & Docker Compose** - Containerization
- **Nginx** - Reverse proxy and static file serving
- **PostgreSQL 15** - Database server

## 📋 Prerequisites

- **Docker** and **Docker Compose** installed
- **Node.js 18+** (for local development)
- **Python 3.9+** (for local development)
- **Git** for version control

## 🚀 Quick Start

### Using Docker (Recommended)

1. **Clone the repository**
   ```bash
   git clone https://github.com/YOUR_USERNAME/msis-forecasting.git
   cd msis-forecasting
   ```

2. **Set up environment variables**
   ```bash
   # Create backend environment file
   cp backend/.env.example backend/.env
   # Edit backend/.env with your configuration
   ```

3. **Start all services**
   ```bash
   docker-compose up -d
   ```

4. **Access the application**
   - Frontend: http://localhost
   - Backend API: http://localhost/api
   - Database: localhost:5432

### Local Development Setup

#### Backend Setup
```bash
# Navigate to backend directory
cd backend

# Create virtual environment
python -m venv venv
source venv/bin/activate  # Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt

# Set up environment variables
cp .env.example .env
# Edit .env with your database configuration

# Run the application
python app.py
```

#### Frontend Setup
```bash
# Navigate to frontend directory
cd Frontend

# Install dependencies
npm install

# Start development server
npm run dev
```

## ⚙️ Configuration

### Environment Variables

Create a `.env` file in the `backend/` directory:

```env

### Database Setup

The application uses PostgreSQL with automatic table creation. Tables include:
- `ships` - Vessel information and specifications
- `positions` - Historical position data
- `routes` - Planned and historical routes
- `users` - Authentication and user management

## 📚 API Documentation

### Authentication Endpoints
- `POST /api/auth/login` - User authentication
- `POST /api/auth/register` - User registration
- `POST /api/auth/logout` - User logout

### Ship Data Endpoints
- `GET /api/ships` - List all ships
- `GET /api/ships/{id}` - Get specific ship details
- `GET /api/ships/types` - Get ship type categories

### Traffic and Analytics
- `GET /api/traffic` - Traffic analysis data
- `GET /api/forecast` - Traffic forecasting
- `GET /api/trends` - Historical trends analysis
- `GET /api/risk-forecast` - Risk assessment data

### Example API Usage
```javascript
// Get ship list
const response = await fetch('/api/ships', {
  headers: {
    'Authorization': `Bearer ${token}`
  }
});
const ships = await response.json();
```

## 🗃️ Data Sources

The system processes ship data from the following sources:
- **AIS Data**: Automatic Identification System broadcasts
- **Ship Registry**: International maritime databases
- **Weather Data**: Meteorological conditions
- **Port Information**: Global port and terminal data

### Data Format
The primary dataset (`ships_with_dynamics_heading.csv`) contains:
- Ship identification (MMSI, IMO, vessel name)
- Position data (latitude, longitude, heading)
- Vessel specifications (type, dimensions, capacity)
- Dynamic information (speed, course, navigation status)

## 🎯 Usage Guide

### Dashboard Navigation
1. **Login/Register** - Secure access to the system
2. **Main Dashboard** - Overview of maritime activity
3. **Interactive Map** - Real-time ship positions and tracking
4. **Traffic Analysis** - Traffic patterns and forecasting
5. **Ship Profiles** - Detailed vessel information
6. **Trends & Analytics** - Historical data analysis

### Key Features
- **Ship Search**: Find specific vessels by name, MMSI, or type
- **Route Planning**: Analyze optimal routes and timing
- **Risk Assessment**: Evaluate operational risks and safety factors
- **Traffic Forecasting**: Predict future traffic patterns
- **Data Export**: Download reports and analysis results

## 🧪 Testing

### Running Tests
```bash
# Backend tests
cd backend
python -m pytest tests/

# Frontend tests
cd Frontend
npm test
```

### Test Coverage
- Unit tests for API endpoints
- Integration tests for database operations
- Frontend component testing
- End-to-end workflow testing

## 🚀 Deployment

### Production Deployment

1. **Configure production environment**
   ```bash
   # Set production environment variables
   export FLASK_ENV=production
   export DEBUG=False
   ```

2. **Build and deploy with Docker**
   ```bash
   docker-compose -f docker-compose.prod.yml up -d
   ```

3. **Set up SSL/TLS** (recommended)
   - Configure SSL certificates in nginx
   - Update nginx.conf for HTTPS

### Monitoring and Logging
- Application logs: `docker-compose logs -f`
- Database monitoring: PostgreSQL log analysis
- Performance metrics: Built-in Flask monitoring

## 🙏 Acknowledgments

- Maritime data providers and AIS networks
- Open-source mapping and visualization libraries
- Flask and React communities
- Docker containerization platform

