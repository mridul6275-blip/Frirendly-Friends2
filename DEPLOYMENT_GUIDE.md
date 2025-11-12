# Deployment Guide - Make Your App Accessible to Anyone

This guide will help you deploy your Friendly Friends App so it's accessible to anyone on the internet.

## Option 1: Deploy to Railway (Recommended - Easiest for Full-Stack)

Railway can host both your backend and frontend in one place.

### Steps:

1. **Sign up at Railway**: Go to https://railway.app and sign up with GitHub

2. **Create New Project**:
   - Click "New Project"
   - Select "Deploy from GitHub repo"
   - Choose your repository

3. **Deploy Backend**:
   - Railway will auto-detect Python
   - Add environment variables:
     - `OPENAI_API_KEY` = your OpenAI API key
     - `FLASK_SECRET_KEY` = generate a random secret key
     - `PORT` = Railway will set this automatically
   - Railway will automatically deploy

4. **Get Backend URL**:
   - Railway will give you a URL like: `https://your-app-name.up.railway.app`
   - Copy this URL

5. **Deploy Frontend**:
   - Create a new service in Railway
   - Select your repo again
   - Set root directory to `frontend`
   - Build command: `npm install && npm run build`
   - Start command: `npx serve -s dist -p $PORT`
   - Add environment variable:
     - `VITE_API_URL` = your backend URL (from step 4)

6. **Update Frontend API URL**:
   - In `frontend/src/services/api.js`, update the base URL to use your Railway backend URL

## Option 2: Deploy Backend to Render + Frontend to Vercel

### Deploy Backend to Render:

1. **Sign up**: Go to https://render.com and sign up

2. **Create Web Service**:
   - Click "New +" → "Web Service"
   - Connect your GitHub repo
   - Settings:
     - Name: `friendly-friends-backend`
     - Environment: `Python 3`
     - Build Command: `pip install -r backend/requirements.txt`
     - Start Command: `cd backend && gunicorn app:app --bind 0.0.0.0:$PORT`
     - Root Directory: `backend`

3. **Environment Variables**:
   - `OPENAI_API_KEY` = your OpenAI API key
   - `FLASK_SECRET_KEY` = generate a random secret key
   - `PYTHON_VERSION` = `3.9`

4. **Get Backend URL**: Render will give you a URL like `https://friendly-friends-backend.onrender.com`

### Deploy Frontend to Vercel:

1. **Sign up**: Go to https://vercel.com and sign up with GitHub

2. **Import Project**:
   - Click "New Project"
   - Import your GitHub repository
   - Root Directory: `frontend`
   - Framework Preset: `Vite`

3. **Environment Variables**:
   - `VITE_API_URL` = your Render backend URL

4. **Deploy**: Click "Deploy"

## Option 3: Deploy Everything to Render (Full-Stack)

1. **Deploy Backend** (same as Option 2)

2. **Deploy Frontend**:
   - Create a new "Static Site" on Render
   - Connect your GitHub repo
   - Root Directory: `frontend`
   - Build Command: `npm install && npm run build`
   - Publish Directory: `frontend/dist`
   - Environment Variable: `VITE_API_URL` = your backend URL

## Quick Setup Files

I've created configuration files to help with deployment:
- `render.yaml` - For Render deployment
- `railway.json` - For Railway deployment
- `vercel.json` - For Vercel frontend deployment

## Important Notes:

1. **Update CORS**: Make sure your backend allows requests from your frontend domain
2. **Database**: For production, consider using PostgreSQL instead of SQLite
3. **File Storage**: For production, use cloud storage (AWS S3, Cloudinary) instead of local uploads
4. **Environment Variables**: Never commit `.env` files - use hosting platform's environment variable settings

## Testing Your Deployment:

1. Visit your frontend URL
2. Try registering a new user
3. Test uploading a video
4. Test AI chat features

## Troubleshooting:

- **CORS Errors**: Update `ALLOWED_ORIGINS` in `backend/app.py` to include your frontend URL
- **Database Issues**: Make sure the database file is being created properly
- **File Uploads**: Check that upload directories have write permissions

Need help? Check the hosting platform's documentation or open an issue!

