🛒 My E-Commerce App

A high-performance, full-stack e-commerce application featuring a seamless Single Page Application (SPA) experience. Built with React, Redux Toolkit, and a Flask backend, this app prioritizes user experience with smooth transitions and secure authentication.

🚀 Key Features

Dynamic Auth Popups: Mutually exclusive Login and Register modals that drop down from the top with custom ease transitions.

Persistent Authentication: Secure JWT-based login with state persistence using localStorage and Redux hydration.

Smart Welcome System: A time-sensitive WelcomeBanner that greets users by name upon login and automatically hides after 5 seconds to clear the UI.

Dark Mode Support: A fully integrated theme switcher that toggles between light and dark modes with persistence.

Robust State Management: Centralized store using Redux Toolkit to manage user sessions, tokens, and loading states globally.

Responsive Navigation: Mobile-friendly navbar with a slide-out menu and conditional rendering for Guest vs. Authenticated users.

🛠️ Tech Stack
## Frontend
React (Vite): Component-based UI architecture.

Redux Toolkit: Advanced state management and asynchronous Thunks for API calls.

Tailwind CSS: Utility-first styling with custom keyframe animations for slide-down effects.

React Icons: Comprehensive iconography for navigation and UI elements.

## Backend
Flask: Lightweight Python web framework.

Flask-JWT-Extended: Secure token-based authentication.

SQLAlchemy: Database ORM for managing users and products.

🔧 Installation & Setup

## Backend Setup
Bash

cd backend
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
pip install -r requirements.txt
flask run

## Frontend Setup
Bash

cd frontend
npm install
npm run dev


🛡️ Authentication Architecture

The app uses a sophisticated "Single Source of Truth" approach for authentication:

Request: User submits credentials via the AuthModal popup.

Thunk: loginUser thunk dispatches an async request to the Flask API.

Response: Backend returns an access_token and a user object.

Reducer: The authSlice handles the fulfillment by saving data to both the Redux state and localStorage, while instantly resetting loading spinners.

UI Feedback: The AuthModal closes automatically, and the WelcomeBanner triggers a personalized greeting.


