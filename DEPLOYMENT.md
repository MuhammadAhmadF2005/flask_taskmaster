# Deployment Guide for Vercel

## Prerequisites
1. Install Vercel CLI: `npm i -g vercel`
2. Have a GitHub account
3. Have a Vercel account

## Database Setup (Required for Production)

### Option 1: Use Vercel Postgres (Recommended)
1. Go to your Vercel dashboard
2. Create a new Postgres database
3. Copy the connection string
4. Add it as an environment variable named `DATABASE_URL` in your Vercel project settings

### Option 2: Use External Database
- Use services like Supabase, Railway, or any PostgreSQL provider
- Add the connection string as `DATABASE_URL` environment variable

## Deployment Steps

### 1. Initialize Database (First Time Only)
```bash
# Run these commands locally first
flask db init
flask db migrate -m "Initial migration"
flask db upgrade
```

### 2. Deploy to Vercel
```bash
# Login to Vercel
vercel login

# Deploy
vercel

# For production deployment
vercel --prod
```

### 3. Set Environment Variables
In your Vercel dashboard:
- Go to your project settings
- Add environment variables:
  - `DATABASE_URL`: Your PostgreSQL connection string
  - `FLASK_ENV`: `production`

### 4. Run Database Migrations on Vercel
After deployment, you'll need to run migrations on the production database:
```bash
# This will run migrations on your production database
vercel env pull .env.production.local
flask db upgrade
```

## Important Notes

1. **Database**: SQLite won't work on Vercel due to serverless architecture. You must use PostgreSQL.

2. **File System**: Vercel uses a read-only file system, so any file operations won't persist.

3. **Environment Variables**: Make sure to set `DATABASE_URL` in your Vercel project settings.

4. **Migrations**: Run database migrations after each deployment if you make schema changes.

## Troubleshooting

- If you get database connection errors, check your `DATABASE_URL` environment variable
- If migrations fail, ensure your database is accessible from Vercel's servers
- Check Vercel function logs for detailed error messages

## Local Development
```bash
# Install dependencies
pip install -r requirements.txt

# Run locally
python main.py
``` 