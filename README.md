# Serios Football League Management System

A comprehensive web application for managing fantasy football leagues with real-time data synchronization from My Fantasy League (MFL). The system provides complete roster management,biddings, contract management, renegotiations and cap sheet generations.

## 📋 Project Summary

This Fantasy Football League Management System is designed to streamline the management of fantasy football leagues by providing automated synchronization with MFL APIs, comprehensive players. The application offers both administrative tools for league managers and user-friendly interfaces for team owners.

### Key Features
- **Real-time MFL Synchronization**: Automated sync with My Fantasy League APIs
- **Comprehensive Player Database**: Master player database with yearly tracking
- **Team Roster Management**: Individual team roster tracking and updates
- **Rookie Draft Integration**: Complete rookie draft tracking
- **Player Scoring Analytics**: Historical and current season scoring data
- **User Authentication**: Secure user management with role-based access
- **Responsive Design**

## 🛠️ Tech Stack

### Frontend
- **Framework**: Next.js
- **Language**: TypeScript
- **Styling**: Tailwind CSS
- **UI Components**: Shadcn/UI
- **State Management**: React Query (TanStack Query)
- **Icons**: Lucide React

### Backend
- **Runtime**: Node.js
- **Framework**: Express.js
- **Database**: PostgreSQL
- **Authentication**: JWT
- **API Integration**: Axios for MFL API calls

### Development Tools
- **Package Manager**: npm/yarn
- **Code Quality**: ESLint, Prettier
- **Version Control**: Git
- **Development Env**: Vistual Studio Code
- 
## 📁 Project Structure

```
├── SFL-Frontend/              # Next.js Frontend Application
│   ├── src/
│   │   ├── app/              # App Router (Next.js)
│   │   ├── components/       # Reusable UI Components
│   │   │   ├── ui/          # Base UI Components (Shadcn)
│   │   │   └── custom/      # Custom Components
│   │   ├── hooks/           # Custom React Hooks
│   │   ├── lib/             # Utility Functions
│   │   └── types/           # TypeScript Type Definitions
│   ├── reactQuery/          # React Query APIs
│   ├── public/              # Static Assets
│   └── package.json
│
├── backend/                   # Express.js Backend API
│   ├── src/
│   │   ├── controllers/     # Route Controllers
│   │   ├── middleware/      # Express Middleware
│   │   ├── routes/          # API Routes
│   │   ├── services/        # Business Logic Services
│   │   ├── utils/           # Utility Functions
│   │   └── config/          # Configuration Files
│   ├── dbscript/            # Database Scripts
│   │   ├── schema.sql       # Database Schema Script
│   │   └── data.sql         # Database Data Script
│   └── package.json
│
├── docs/                     # Documentation
├── .env.example             # Environment Variables Template
└── README.md               # Project Documentation
```

## 🔄 Project Flow

### 1. **User Authentication Flow**
```
User Login → JWT Token Generation → Protected Route Access → Bidding Platform
```

### 2. **MFL Data Synchronization Flow**
```
Manual/Scheduled Sync → MFL API Calls → Data Processing → Database Updates → UI Refresh
```

### 3. **Bidding Platform Flow**
```
Dashboard → Bidding Platform → [Ongoing Bids | Expired Bids] → Bid Card Click → Bidding Page
   ↓
Player Wins Bid → Add Player to Roster (MFL Official Site) → Contract Editor
```

### 4. **Contract Management Flow**
```
Contract Editor → View Player Details → Sign Contract → Contract Database Update
```

### 5. **Renegotiation Flow**
```
Renegotiation Module → Calculation Engine → [Voluntary Section | Forced Section] → Contract Categorized
```

### 6. **User Administration Flow**
```
Admin Login → User Administrator → Add User Details → Email Generation → User Login Credentials
```

### 7. **Administrator Options Flow**
```
 Administrator Options → [Close Year | Start New Year | Change Active Phase | 
Update MFL Credentials | Edit Contracts | Edit Auctions] → System Updates
```

### 8. **Audit Reports Flow**
```
Audit Reports → Filter Actions → Generate Reports → View Action Records
```

### 9. **Cap Sheet Generator Flow**
```
Cap Sheet Generator → [Default User Team | Select Multiple Teams] → Select Year → Generate Sheet
```

### 10. **Data Sync Process**
```
Step 1: Sync All Players (Master Database)
   ↓
Step 2: Sync Team Rosters (Team-specific Data)
   ↓
Step 3: Sync Player Scoring (Historical Data)
   ↓
Step 4: Sync Rookie Draft (Draft Information)
   ↓
Step 5: Update UI with Results
```

## 🏗 Module Details

### 1. **Authentication Module**
- **Purpose**: User authentication and authorization
- **Features**: Login/logout, JWT token management, role-based access
- **Components**: Login

### 2. **MFL Synchronization Module**
- **Purpose**: Data synchronization with My Fantasy League
- **Features**: 
  - All players sync (master database)
  - Team roster sync (specific team data)
  - Player scoring sync (points data)
  - Rookie draft sync (draft information)
- **Components**: Sync status UI, progress tracking

### 3. **Bidding Platform Module**
- **Purpose**: Comprehensive player bidding and auction system
- **Features**: 
  - Ongoing bids management
  - Expired bids tracking
  - Individual bidding pages
  - Real-time bid updates
- **Components**: Bidding-Platform, bidding interface, bid history

### 4. **Contract Editor Module**
- **Purpose**: Player contract management after successful bids
- **Features**: 
  - Player contract signing
  - Contract terms management
  - Contract status tracking
  - Integration with MFL roster updates
- **Components**: Contract Editor

### 5. **Renegotiation Module**
- **Purpose**: Contract renegotiation with calculation engine
- **Features**: 
  - Calculation algorithms for renegotiation
  - Voluntary renegotiation section
  - Forced renegotiation section
  - Contract modification tracking
- **Components**: renegotiation , Calculation interface, renegotiation forms

### 6. **User Administrator Module**
- **Purpose**: User management and administration
- **Features**: 
  - Add new users with required details
  - User role management
- **Components**: User forms, user listing

### 7. **Administrator Options Module**
- **Purpose**: System administration and configuration
- **Features**: 
  - Close/Start fantasy year
  - Change active phase
  - Update MFL credentials
  - Edit contracts and auctions
- **Components**: Admin Options

### 8. **Audit Reports Module**
- **Purpose**: System activity tracking and reporting
- **Features**: 
  - Action logging and tracking
  - Report generation
  - User activity monitoring
  - System change history
- **Components**: Audit Reports, Report tables, filtering options

### 9. **Cap Sheet Generator Module**
- **Purpose**: Salary cap management and reporting
- **Features**: 
  - Default user team selection
  - Multiple team selection
  - Year-based sheet generation
  - Salary cap calculations
- **Components**: Cap Sheet Generator, Team selector, year picker, cap sheet tables



## 🚀 Local Setup Instructions

### Prerequisites
- Node.js 
- pgAdmin 4 (for database management)
- npm or yarn package manager
- Git

### 1. Clone the Repositories in Individual Folders (Frontend | Backend)
```bash
#Frontend Repo
git clone https://github.com/surajm-kinetic-data/SFL-frontend.git
cd SFL-Frontend

#Backend Repo
git clone https://github.com/surajm-kinetic-data/SFL-Backend.git
cd Backend
```


### 2. Environment Configuration

#### Backend Environment (.env)
Create a `.env` file in the backend directory:
```env


DB_HOST = 'localhost'
DB_PASSWORD = 'your password' 
DB_USER = 'postgres'
DB_NAME = 'db_name'
# __dirname =''

#Email Setup (Right now it is demo credentials can use, we will need to create different for SFL official email from googleaccounts)
SMTP_EMAIL = 'u3147192@gmail.com'
SMTP_PASSWORD = 'iuol rsep gvbs nejd'

#Server Port
PORT=5000


#JWT Secret key
Secret_Key=Keep anything mixed value (eg:ndfbej43ieiindfnf)

#(original sfl leagueid)
LEAGUE_ID=32201
 #(test league id)  
TEST_LEAGUE_ID=58450 
MFL_API_KEY=your_mfl_api_key

DB_PORT=5432

```

#### Frontend Environment (.env.local)
Create a `.env.local` file in the frontend directory:
```env
NEXT_PUBLIC_API_BASE_URL =  http://localhost:5000
```

### 3. Database Setup

#### Install and Setup PostgreSQL with pgAdmin 4
```bash
# Install PostgreSQL (varies by OS)
# For Ubuntu/Debian:
sudo apt-get install postgresql postgresql-contrib

# For macOS (using Homebrew):
brew install postgresql

# For Windows: Download from postgresql.org
```

#### Setup Database using pgAdmin 4
1. **Open pgAdmin 4**
2. **Connect/Add PostgreSQL Server**
   - Name: `SFL`
   - Host: `localhost`
   - Port: `5432`
   - Username: `postgres`
   - Password: `your_postgres_password`

3. **Create Database**
   - Right-click on server → Create → Database
   - Database name: `SFL`
   - Owner: `postgres` (or create a specific user)

4. **Import Database Scripts**
   
   **Method 1: Using pgAdmin Query Tool**
   - Right-click on `fantasy_football_db` → Query Tool
   - Open and execute `backend/dbscript/schema.sql`
   - Then execute `backend/dbscript/data.sql`
  


### 4. Backend Setup
```bash
# Navigate to backend directory
cd backend

# Install dependencies
npm install


# Start development server
nodemon server.js or npm start
```

### 5. Frontend Setup
```bash
# Open new terminal and navigate to frontend directory
cd SFL-Frontend

# Install dependencies
npm install

# Start development server
npm run dev
```

### 6. Access the Application
- **Frontend**: http://localhost:3000
- **Backend API**: http://localhost:5000

## 🔑 API Keys and Credentials Setup

### MFL API Configuration
1. **Get MFL API Access**:
   - Contact My Fantasy League for API access
   - Obtain your league-specific API key
   - Get your league ID from your MFL league URL

2. **League ID Location**:
   - Found in your MFL league URL: `https://www.myfantasyleague.com/2024/home/LEAGUE_ID`
   - Also available in league settings

### 3. Database Connection Test
Check backend console logs for successful database connection messages.


## 🔧 Development Scripts

### Backend
```bash

nodemon server.js or npm start       # Start backend
```

### Frontend
```bash
npm run dev         # Start frontend
```


---

**Note**: This application requires active My Fantasy League API access and proper configuration of all environment variables to function correctly.
