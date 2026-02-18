# RentEase - Frontend

A modern React-based web application for managing rental properties and connecting property owners with renters.

## 📋 Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Tech Stack](#tech-stack)
- [Project Structure](#project-structure)
- [Installation & Setup](#installation--setup)
- [Available Scripts](#available-scripts)
- [Components Overview](#components-overview)
- [Authentication & Routing](#authentication--routing)
- [API Integration](#api-integration)
- [Key Technologies](#key-technologies)

## 🏠 Overview

RentEase is a full-stack rental property platform that enables users to:
- Browse available rental properties
- List and manage properties as property owners
- Book properties as renters
- Manage user accounts and bookings
- Administrative controls for platform management

The frontend is built with React and provides an intuitive user interface with role-based access for different user types (Admin, Owner, and Renter).

## ✨ Features

### Authentication
- User **Login** and **Registration**
- **Password Recovery** (Forgot Password)
- Role-based access control
- Persistent session using localStorage

### Admin Features
- View all users
- View all properties
- Monitor all bookings
- Manage platform data

### Owner Features
- Add and manage properties
- Upload property images
- View property listings
- Track bookings for their properties

### Renter Features
- Browse all available properties
- View property details
- Make property bookings
- Track booking history

## 🛠 Tech Stack

- **React** 18.2.0 - UI framework
- **React Router DOM** 6.15.0 - Client-side routing
- **Bootstrap 5** & **React Bootstrap** - Responsive UI components
- **Material-UI (MUI)** - Advanced UI components
  - `@mui/material`
  - `@mui/icons-material`
  - `@mui/joy`
- **Ant Design (antd)** - UI library with message notifications
- **Axios** - HTTP client for API requests
- **Emotion** - CSS-in-JS styling

## 📁 Project Structure

```
frontend/
├── public/
│   └── index.html              # Main HTML file
├── src/
│   ├── App.js                  # Root component with routing
│   ├── App.css                 # Global styles
│   ├── index.js                # React entry point
│   ├── images/                 # Image assets
│   └── modules/                # Feature modules
│       ├── common/             # Shared authentication pages
│       │   ├── Home.jsx        # Landing page with property carousel
│       │   ├── Login.jsx       # User login page
│       │   ├── Register.jsx    # User registration
│       │   └── ForgotPassword.jsx
│       ├── admin/              # Administrator dashboard
│       │   ├── AdminHome.jsx   # Admin dashboard
│       │   ├── AllUsers.jsx    # User management
│       │   ├── AllProperty.jsx # Property management
│       │   └── AllBookings.jsx # Booking oversight
│       └── user/               # User-specific features
│           ├── AllPropertiesCards.jsx  # Shared property listing component
│           ├── Owner/          # Property owner features
│           │   ├── OwnerHome.jsx
│           │   ├── AddProperty.jsx    # Property creation form
│           │   ├── AllProperties.jsx
│           │   └── AllBookings.jsx
│           └── renter/         # Renter features
│               ├── RenterHome.jsx
│               └── AllProperties.jsx
├── package.json
└── .gitignore
```

## 🚀 Installation & Setup

### Prerequisites
- Node.js (v14 or higher)
- npm or yarn package manager

### Steps

1. **Navigate to frontend directory**
   ```bash
   cd frontend
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Configure API endpoint** (if needed)
   - Update API base URL in components using axios
   - Ensure backend server is running on the configured port

4. **Start the development server**
   ```bash
   npm start
   ```

The application will open at `http://localhost:3000`

## 📜 Available Scripts

In the frontend directory, you can run:

### `npm start`
Runs the app in development mode with hot reloading.
Open [http://localhost:3000](http://localhost:3000) to view it in your browser.

### `npm build`
Builds the app for production to the `build` folder.
Optimizes the build for the best performance.

### `npm test`
Launches the test runner in interactive watch mode.

### `npm eject`
**Note: this is a one-way operation. Once you eject, you can't go back!**

## 🧩 Components Overview

### Common Components
- **Home.jsx** - Landing page featuring property carousel and featured listings
- **Login.jsx** - User authentication form
- **Register.jsx** - New user registration form
- **ForgotPassword.jsx** - Password recovery functionality
- **AllPropertiesCards.jsx** - Reusable property card component

### Admin Components
- **AdminHome.jsx** - Main admin dashboard
- **AllUsers.jsx** - Display and manage all platform users
- **AllProperty.jsx** - View and manage all listed properties
- **AllBookings.jsx** - Monitor all bookings across the platform

### Owner Components
- **OwnerHome.jsx** - Owner dashboard
- **AddProperty.jsx** - Form to list new rental properties (supports image upload)
- **AllProperties.jsx** - Manage owner's property listings
- **AllBookings.jsx** - View bookings for owner's properties

### Renter Components
- **RenterHome.jsx** - Renter dashboard
- **AllProperties.jsx** - Browse all available properties

## 🔐 Authentication & Routing

### User Context
The app uses React Context API (`UserContext`) to manage:
- `userData` - Current logged-in user information
- `userLoggedIn` - Authentication status

### Protected Routes
- `/adminhome` - Only accessible to authenticated users with admin role
- `/ownerhome` - Only accessible to authenticated users with owner role
- `/renterhome` - Only accessible to authenticated users with renter role

### Public Routes
- `/` - Home page
- `/login` - Login page
- `/register` - Registration page
- `/forgotpassword` - Password recovery

### Session Persistence
User data is stored in `localStorage` and restored on app reload.

## 🔌 API Integration

The frontend communicates with the backend API using **Axios**. Key features:

- **Form Submissions** - Property creation, user registration, login
- **Image Uploads** - FormData for multipart/form-data requests (in AddProperty.jsx)
- **Data Fetching** - Retrieving properties, users, bookings
- **Error Handling** - Ant Design messages for user feedback

### Example API Call (AddProperty.jsx)
```javascript
const formData = new FormData();
formData.append('propertyType', propertyDetails.propertyType);
// ... append other fields and images
// API call to backend endpoint
```

## 🎨 Key Technologies

| Technology | Purpose |
|-----------|---------|
| **React** | UI framework and component management |
| **React Router** | Client-side navigation and routing |
| **Bootstrap/MUI** | Responsive UI design |
| **Axios** | HTTP requests and API communication |
| **Context API** | Global state management for user data |
| **Ant Design** | Form validations and notifications |

## 📝 Notes

- The app includes a responsive navbar that adapts to different screen sizes
- Footer displays current year dynamically
- Images are stored and served from the backend `/uploads` directory
- Authentication uses localStorage; consider implementing more secure methods for production
- All forms include input validation and user feedback through Ant Design messages

## 🔗 Additional Resources

- [Project Documentation](https://docs.google.com/document/d/1AUCuc2DxWLhj1f5vSLCVVNFqPeGeWuFh/edit?usp=sharing&ouid=103693589633357475993&rtpof=true&sd=true)
- [Demo Video](https://drive.google.com/file/d/1QioacNtT-l7T0bDTW96vL7Sv6mnhY3J3/view?usp=sharing)

---

**Happy coding! 🎉**

