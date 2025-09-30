# Backend Deployment Guide

## Environment Variables Required

Set these environment variables in your Vercel dashboard:

```
SECRET_KEY=your-secret-key-here
DEBUG=False
OPENAI_API_KEY=your-openai-api-key-here (optional)
```

## Deployment Steps

1. **Install Vercel CLI** (if not already installed):
   ```bash
   npm i -g vercel
   ```

2. **Deploy to Vercel**:
   ```bash
   cd backend
   vercel --prod
   ```

3. **Set Environment Variables** in Vercel Dashboard:
   - Go to your project settings
   - Add the environment variables listed above

## Common Issues

1. **Database Issues**: SQLite doesn't work well on Vercel. Consider using:
   - PostgreSQL with Vercel Postgres
   - MongoDB Atlas
   - Supabase

2. **Static Files**: Make sure to run `python manage.py collectstatic` before deployment

3. **CORS Issues**: Update CORS_ALLOWED_ORIGINS with your frontend domain

## Testing the API

After deployment, test your API endpoints:
- Health check: `GET /api/`
- User registration: `POST /api/auth/register/`
- User login: `POST /api/auth/login/`
