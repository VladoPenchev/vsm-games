# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Development Commands

- `npm run dev` - Start development server with Vite
- `npm run build` - Build for production (TypeScript compilation + Vite build)
- `npm run lint` - Run ESLint with TypeScript support
- `npm run preview` - Preview production build locally

## AWS Amplify Commands

- `npx ampx sandbox` - Start local Amplify sandbox environment
- `npx ampx pipeline-deploy --branch $AWS_BRANCH --app-id $AWS_APP_ID` - Deploy backend to AWS

## Architecture Overview

This is a React + Vite application built on AWS Amplify Gen 2 with the following stack:

### Frontend
- **React 18** with TypeScript
- **Vite** for build tooling and dev server
- **AWS Amplify UI React** components for authentication UI
- Main application logic in `src/App.tsx`

### Backend (AWS Amplify)
- **Authentication**: Amazon Cognito with email-based login (`amplify/auth/resource.ts`)
- **Data**: GraphQL API with AWS AppSync + DynamoDB (`amplify/data/resource.ts`)
- **Schema**: Single `Todo` model with `content` field, public API key authorization
- Backend definition in `amplify/backend.ts`

### Data Flow
- Uses `generateClient<Schema>()` from aws-amplify/data for GraphQL operations
- Real-time subscriptions via `observeQuery()` for live updates
- Todo CRUD operations: create via prompt, delete on click

### Key Files
- `src/App.tsx` - Main React component with todo functionality and authentication
- `amplify/data/resource.ts` - GraphQL schema and data model definitions
- `amplify/auth/resource.ts` - Authentication configuration
- `amplify/backend.ts` - Backend resource composition
- `amplify_outputs.json` - Generated Amplify configuration (auto-generated)

### Authentication Integration
- Uses `useAuthenticator` hook for sign-out functionality
- Authentication UI components wrap the app (likely in `src/main.tsx`)
- API uses public API key authorization mode with 30-day expiration

## Development Notes

- TypeScript strict mode enabled
- ESLint configured for React with TypeScript
- No test framework currently configured
- Build output goes to `dist/` directory
# important-instruction-reminders
Do what has been asked; nothing more, nothing less.
NEVER create files unless they're absolutely necessary for achieving your goal.
ALWAYS prefer editing an existing file to creating a new one.
NEVER proactively create documentation files (*.md) or README files. Only create documentation files if explicitly requested by the User.