# MicroTech Dashboard

A comprehensive admin dashboard for managing MicroTech's internal operations, projects, team members, and resources.

## Overview

MicroTech Dashboard is a Next.js-based administrative interface that provides a centralized platform for managing various aspects of the MicroTech organization. It includes features for project management, team coordination, technology tracking, and resource management.

## Features

- **Project Management**: Create, view, edit, and manage projects with detailed information
- **Technology Management**: Track and manage technologies used across projects
- **Tools Kit Management**: Organize and manage development tools and resources
- **Platform Management**: Manage different platforms and deployment environments
- **Work Types Management**: Categorize and manage different types of work
- **Member Management**: Manage team members and their roles
- **Settings**: Configure dashboard settings and preferences
- **Authentication**: Secure login and verification system with JWT tokens
- **Dark Mode**: Built-in theme switching support
- **Responsive Design**: Fully responsive layout optimized for all screen sizes

## Tech Stack

### Core Framework

- **Next.js 14.2.3** - React framework with App Router
- **React 18** - UI library
- **TypeScript 5** - Type safety

### UI Components & Styling

- **Tailwind CSS 3.4.1** - Utility-first CSS framework
- **Radix UI** - Accessible component primitives
  - Dialog, Dropdown Menu, Popover, Select, Tabs, Tooltip, Checkbox, Label, Separator
- **Lucide React** - Icon library
- **React Icons** - Additional icon set
- **next-themes** - Theme management
- **tailwindcss-animate** - Animation utilities
- **class-variance-authority** - Component variant management
- **clsx** & **tailwind-merge** - Conditional class utilities

### Forms & Validation

- **React Hook Form 7.51.4** - Form state management
- **Zod 3.23.8** - Schema validation
- **@hookform/resolvers** - Form validation resolvers

### Data Management

- **Axios 1.6.8** - HTTP client with interceptors
- **Zustand 4.5.2** - State management
- **TanStack React Table 8.17.3** - Data table component

### UI Enhancements

- **Sonner 1.4.41** - Toast notifications
- **cmdk** - Command menu component
- **input-otp** - OTP input component
- **react-cookie** - Cookie management

## Prerequisites

- Node.js 18+
- npm, yarn, pnpm, or bun
- Access to the MicroTech API backend

## Installation

1. Clone the repository:

```bash
git clone <repository-url>
cd microtech-dashboard
```

2. Install dependencies:

```bash
npm install
# or
yarn install
# or
pnpm install
```

3. Create a `.env.local` file in the root directory:

```env
NEXT_PUBLIC_BASE_URL=your-api-base-url
```

## Configuration

### Environment Variables

Create a `.env.local` file with the following variables:

- `NEXT_PUBLIC_BASE_URL` - Base URL for the API backend (e.g., `https://adminpanel.microtechdev.com`)

### Next.js Configuration

The project is configured for static export. Image optimization is set up for remote patterns including:

- `adminpanel.microtechdev.com`
- `127.0.0.1` (for local development)

## Available Scripts

- `npm run dev` - Start development server on port 3008
- `npm run build` - Build the application for production
- `npm run start` - Start the production server
- `npm run lint` - Run ESLint to check code quality

## Project Structure

```
microtech-dashboard/
├── app/
│   ├── (dashboard)/          # Dashboard routes
│   │   ├── (routes)/         # Main dashboard pages
│   │   │   ├── members/      # Member management
│   │   │   ├── platforms/   # Platform management
│   │   │   ├── projects/     # Project management
│   │   │   ├── settings/     # Settings page
│   │   │   ├── technologies/ # Technology management
│   │   │   ├── tools-kit/    # Tools kit management
│   │   │   └── work-types/   # Work types management
│   │   ├── _components/      # Dashboard components
│   │   │   ├── navbar.tsx
│   │   │   └── sidebar.tsx
│   │   └── layout.tsx
│   ├── auth/                 # Authentication routes
│   │   └── (routes)/
│   │       ├── login/
│   │       └── _register/
│   ├── globals.css
│   └── layout.tsx
├── components/
│   ├── auth/                 # Authentication components
│   ├── modals/               # Modal components
│   └── ui/                   # Reusable UI components
├── config/
│   └── site.ts              # Site configuration and routes
├── hooks/                    # Custom React hooks
├── lib/
│   ├── axios.ts             # Axios configuration and interceptors
│   └── utils.ts             # Utility functions
├── providers/                # Context providers
│   ├── auth-provider.tsx
│   └── theme-provider.tsx
└── schemas/
    └── index.ts             # Zod validation schemas
```

## Authentication

The dashboard uses JWT-based authentication with automatic token refresh:

- Access tokens are stored in localStorage
- Automatic token refresh on 401 responses
- Protected routes require authentication
- OTP verification for additional security

## API Integration

The application uses Axios with:

- Automatic authorization header injection
- Request/response interceptors
- Error handling with toast notifications
- Token refresh mechanism
- Abstract classes for data fetching and authentication

## Development

### Running in Development Mode

```bash
npm run dev
```

The application will be available at `http://localhost:3008`

### Building for Production

```bash
npm run build
npm run start
```

## Features in Detail

### Project Management

- View all projects in a data table
- Create new projects
- Edit existing projects
- Delete projects
- View project details

### Data Tables

All management pages use TanStack React Table for:

- Sorting
- Filtering
- Pagination
- Column visibility

### Theme Support

- Light and dark mode
- Persistent theme preference
- Smooth theme transitions

## Contributing

1. Create a feature branch
2. Make your changes
3. Ensure all linting passes
4. Submit a pull request

## License

Private - MicroTech Internal Use Only
