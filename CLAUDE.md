# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a Next.js 15 starter project with Appwrite integration for a roofing landing platform. The project uses React 19, Tailwind CSS v4, and includes a demo connection testing interface to verify Appwrite backend connectivity.

## Available Commands

- `npm run dev` - Start development server (Next.js dev mode)
- `npm run build` - Build production application
- `npm run start` - Start production server
- `npm run lint` - Run ESLint for code quality checks

## Development Setup

1. Install dependencies: `npm install`
2. Configure environment variables in `.env`:
   - `NEXT_PUBLIC_APPWRITE_PROJECT_ID` - Appwrite project ID
   - `NEXT_PUBLIC_APPWRITE_PROJECT_NAME` - Display name for project
   - `NEXT_PUBLIC_APPWRITE_ENDPOINT` - Appwrite server endpoint URL
3. Run development server: `npm run dev`

## Architecture

### File Structure
```
src/
├── app/                 # Next.js App Router directory
│   ├── layout.js       # Root layout with fonts and metadata
│   ├── page.js         # Main homepage with Appwrite connection demo
│   └── app.css         # Global CSS styles
├── lib/                # Shared utilities and configurations
│   └── appwrite.js     # Appwrite client, account, and databases setup
└── static/             # Static assets (SVG icons)
```

### Key Components

- **Main Page (`src/app/page.js`)**: Interactive demo showing Next.js + Appwrite connection with:
  - Connection testing via ping API
  - Real-time logs display in expandable footer
  - Environment variable display for debugging
  - Responsive UI with loading states and status indicators

- **Appwrite Integration (`src/lib/appwrite.js`)**: Centralized Appwrite client configuration with exported instances for client, account, and databases services

- **Layout (`src/app/layout.js`)**: Root layout with Inter and Poppins fonts, custom favicon, and global styling

### Styling

- **Tailwind CSS v4**: Modern utility-first CSS framework
- **Custom CSS**: Located in `src/app/app.css` for additional styling
- **Fonts**: Inter (primary), Poppins (headings), Fira Code (code blocks)
- **Theme**: Light theme with custom color palette focused on Appwrite pink (#FD366E)

## Code Quality Standards

The project follows the clean code guidelines defined in `CleanCodeRules.md`:
- Use meaningful variable and function names
- Keep functions small and focused (single responsibility)
- Replace magic numbers with named constants
- Write self-documenting code minimizing comments
- Extract repeated code into reusable functions
- Maintain consistent file and folder naming

## Environment Configuration

All Appwrite configuration is handled through environment variables prefixed with `NEXT_PUBLIC_` to make them available in the browser. The main page displays these values for debugging purposes.

## Testing Appwrite Connection

The application includes a built-in connection testing feature on the main page that:
- Sends ping requests to verify Appwrite connectivity
- Displays connection status with visual feedback
- Logs all API requests with timestamps, status codes, and responses
- Shows environment configuration for debugging