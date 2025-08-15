# Full-Stack Leasing Management Application

A comprehensive leasing management system built with React, Node.js, Express, and SQLite. This application allows admins to manage owners, tenants, properties, units, and leases efficiently.

## Features

### Admin Authentication
- Secure login system with JWT tokens
- Pre-seeded admin account

### Contact Management
- Create and manage owners and tenants
- Detailed contact information forms
- View all contacts in organized lists

### Property Portfolio
- Add properties with comprehensive details
- Automatic unit creation (2 units per property)
- Track property stages and types

### Lease Management
- Create leases linking tenants to units
- Automatic unit status updates (Available → Occupied)
- Track lease periods, rent amounts, and contract types
- Comprehensive lease overview with financial summaries

### Dashboard
- Real-time statistics and analytics
- Occupancy rate tracking
- Financial overview

## Tech Stack

**Frontend:**
- React 18 with TypeScript
- Tailwind CSS for styling
- React Router for navigation
- Lucide React for icons

**Backend:**
- Node.js with Express
- SQLite database
- JWT authentication
- bcryptjs for password hashing

## Installation & Setup

### Prerequisites
- Node.js (v16 or higher)
- npm

### 1. Install Dependencies
```bash
npm install
```

### 2. Start the Backend Server
```bash
node server.js
```
The server will start on `http://localhost:3001`

### 3. Start the Frontend Development Server
```bash
npm run dev
```
The application will be available at `http://localhost:5173`

## Admin Login Credentials

```
Username: admin
Password: admin123
```

## Database Schema

The application uses SQLite with the following tables:

- **admins**: Admin user credentials
- **owners**: Property owner information
- **tenants**: Tenant contact details
- **properties**: Property information and details
- **units**: Individual units linked to properties
- **leases**: Lease agreements linking tenants to units

## API Endpoints

### Authentication
- `POST /api/auth/login` - Admin login

### Owners
- `GET /api/owners` - Get all owners
- `POST /api/owners` - Create new owner

### Tenants
- `GET /api/tenants` - Get all tenants
- `POST /api/tenants` - Create new tenant

### Properties
- `GET /api/properties` - Get all properties
- `POST /api/properties` - Create new property (automatically creates 2 units)

### Units
- `GET /api/units` - Get all units with property information

### Leases
- `GET /api/leases` - Get all leases with tenant, unit, and property details
- `POST /api/leases` - Create new lease (automatically updates unit status)

## Usage Workflow

1. **Login** using the admin credentials
2. **Create Contacts**: Add owners and tenants with their information
3. **Add Properties**: Create properties (automatically generates 2 units each)
4. **Create Leases**: Assign tenants to available units
5. **Monitor**: Use the dashboard to track occupancy and financial metrics

## Key Features

- **Responsive Design**: Works seamlessly on desktop and mobile devices
- **Real-time Updates**: Automatic status updates when leases are created
- **Data Validation**: Comprehensive form validation and error handling
- **Secure Authentication**: JWT-based authentication with protected routes
- **Clean UI**: Professional interface matching modern design standards

## Project Structure

```
node_modules/
src/
├── components/          # React components
│   ├── Layout.tsx      # Main layout with navigation
│   ├── Login.tsx       # Authentication component
│   ├── Dashboard.tsx   # Statistics and overview
│   ├── Contacts.tsx    # Owner/tenant management
│   ├── Portfolio.tsx   # Property/unit management
│   └── Leases.tsx      # Lease management
├── contexts/           # React contexts
│   └── AuthContext.tsx # Authentication state management
├── utils/              # Utility functions
│   └── api.ts          # API client functions
└── App.tsx            # Main application component
```

## Development Notes

- The database is initialized in memory and will reset when the server restarts
- All forms include proper validation and error handling
- The UI closely matches the provided design specifications
- Units are automatically marked as "Occupied" when leases are created
- The application includes comprehensive error handling and loading states

## Future Enhancements

- Persistent database (PostgreSQL/MySQL)
- Payment tracking and management
- Document upload and management
- Email notifications
- Advanced reporting and analytics
- Multi-tenant support
