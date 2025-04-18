# Battery Manager Deployment Guide

This document provides instructions for deploying the Battery Manager application.

## Prerequisites

- Node.js 18+ and npm
- PostgreSQL database
- Clerk account for authentication
- Twilio account for WhatsApp integration (optional)

## Frontend Deployment

The frontend is built with Next.js and can be deployed to Vercel:

1. Create a Vercel account if you don't have one
2. Connect your GitHub repository to Vercel
3. Configure the following environment variables:
   - `NEXT_PUBLIC_API_URL`: URL of your backend API
   - `NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY`: Your Clerk publishable key

Alternatively, you can build and deploy the frontend manually:

```bash
cd frontend
npm run build
# Deploy the build output to your hosting provider
```

## Backend Deployment

The backend can be deployed to Render, Fly.io, or any other Node.js hosting service:

1. Set up a PostgreSQL database
2. Configure the following environment variables:
   - `DATABASE_URL`: PostgreSQL connection string
   - `PORT`: Port for the server (default: 5000)
   - `NODE_ENV`: Set to "production"
   - `CLERK_SECRET_KEY`: Your Clerk secret key
   - `TWILIO_ACCOUNT_SID`: Your Twilio account SID (for WhatsApp)
   - `TWILIO_AUTH_TOKEN`: Your Twilio auth token (for WhatsApp)

### Deployment Steps for Render

1. Create a new Web Service in Render
2. Connect your GitHub repository
3. Set the build command: `cd backend && npm install && npx prisma generate && npm run build`
4. Set the start command: `cd backend && npm start`
5. Add the environment variables listed above

## Database Setup

Before deploying, you need to set up the database:

1. Create a PostgreSQL database
2. Update the `DATABASE_URL` in the backend `.env` file
3. Run migrations:

```bash
cd backend
npx prisma migrate deploy
```

## Post-Deployment Verification

After deployment, verify that:

1. Frontend can connect to the backend API
2. Authentication works correctly
3. All CRUD operations function as expected
4. PDF/Excel exports work
5. Multilingual support works
6. WhatsApp integration works (if configured)

## Troubleshooting

- If the frontend can't connect to the backend, check CORS settings in the backend
- If database operations fail, verify the database connection string
- If authentication fails, check Clerk configuration
- For WhatsApp integration issues, verify Twilio credentials

## Maintenance

- Regularly backup the database
- Monitor server logs for errors
- Update dependencies periodically for security patches
