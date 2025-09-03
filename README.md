# Nuxt 3 JWT Application

A modern real-time chat application built with Nuxt 3, featuring JWT authentication and a beautiful user interface.

## 🚀 Features

- **JWT Authentication**: Secure login/register with JWT tokens
- **Modern UI**: Built with Tailwind CSS and Element Plus

## 🛠️ Tech Stack

- **Frontend**: Nuxt 3, Vue 3, TypeScript
- **Styling**: Tailwind CSS, Element Plus
- **State Management**: Pinia
- **Authentication**: JWT with HTTP-only cookies
- **Icons**: Nuxt Icon
- **Images**: Nuxt Image
- **Linting**: ESLint
- **HTTP Client**: Axios with interceptors

## 📦 Installation

### Prerequisites

- Node.js >= 22
- Yarn or npm

### Install Dependencies

```bash
# Using yarn (recommended)
yarn install

# Or using npm
npm install
```

## ⚙️ Configuration

### Environment Variables

Create a `.env` file in the root directory:

```env
# Backend API URL
BACKEND_URL=http://localhost:8080

# Frontend URL
FRONTEND_URL=http://localhost:3000

# Environment
ENVIRONMENT=development
```

### Nuxt Configuration

The project uses the following modules:

- `@nuxt/eslint` - Code linting
- `@nuxt/icon` - Icon management
- `@nuxt/image` - Image optimization
- `@nuxtjs/tailwindcss` - Tailwind CSS integration
- `@element-plus/nuxt` - Element Plus UI components
- `@pinia/nuxt` - State management

## 🚀 Running the Application

### Development

```bash
# Start development server
yarn dev

# Or
npm run dev
```

The application will be available at `http://localhost:3000`

### Production

```bash
# Build the application
yarn build

# Preview production build
yarn preview

# Generate static site
yarn generate
```

## 📁 Project Structure

```
nuxt-3-jwt/
├── assets/                 # Static assets
│   ├── css/               # CSS files
│   └── images/            # Images
├── components/            # Vue components
│   └── Modules/          # Feature-based components
│       └── Auth/         # Authentication components
├── composables/          # Vue composables
├── layouts/              # Layout components
├── middleware/           # Route middleware
├── pages/                # Pages (auto-routing)
├── plugins/              # Nuxt plugins
├── server/               # Server-side code
│   ├── api/             # API routes
│   └── utils/           # Server utilities
├── stores/               # Pinia stores
├── types/                # TypeScript type definitions
└── utils/                # Utility functions
```

## 🔐 Authentication

### Authentication Flow

1. **Login**: User enters email/password
2. **JWT Token**: Server returns access token
3. **Cookie Storage**: Token stored in HTTP-only cookie
4. **Middleware**: Token validation for protected routes
5. **Auto-refresh**: Automatic token verification when needed

### Protected Routes

Use the `auth.global.ts` middleware to protect routes:

```typescript
// In page component
definePageMeta({
  requireAuth: true,
});
```

### Authentication Composable

The `useAuthentication` composable provides:

- `useAuthentication()` - Get current auth state
- `useLogin()` - Login user and set token
- `useAuthorization()` - Verify token and refresh auth state
- `useLogout()` - Logout user and clear token

## 🎨 UI Components

### Authentication Components

- **Login Form**: Email/password login with validation
- **Register Form**: User registration with form validation
- **Password Toggle**: Show/hide password functionality
- **Error Handling**: User-friendly error messages

## 🔧 API Endpoints

### Authentication API

- `POST /api/auth/login` - User login
- `POST /api/auth/register` - User registration
- `GET /api/auth/verify` - Token verification