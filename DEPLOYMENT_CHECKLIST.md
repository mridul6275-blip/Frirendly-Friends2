# Production Deployment Checklist

## Before Deploying:

- [ ] Update CORS settings in `backend/app.py` to include your frontend URL
- [ ] Set all environment variables on your hosting platform
- [ ] Update `frontend/src/services/api.js` to use production API URL
- [ ] Test locally with production settings
- [ ] Ensure database migrations are handled
- [ ] Set up file storage (consider cloud storage for production)

## Environment Variables Needed:

### Backend:
- `OPENAI_API_KEY` - Your OpenAI API key
- `FLASK_SECRET_KEY` - Random secret key (generate with: `python -c "import secrets; print(secrets.token_hex(32))"`)
- `FRONTEND_URL` - Your frontend deployment URL
- `PORT` - Usually set automatically by hosting platform

### Frontend:
- `VITE_API_URL` - Your backend deployment URL

## Quick Deploy Commands:

### Railway:
```bash
# Install Railway CLI
npm i -g @railway/cli

# Login
railway login

# Link project
railway link

# Deploy
railway up
```

### Render:
Just connect your GitHub repo - Render will auto-deploy on push!

### Vercel:
```bash
# Install Vercel CLI
npm i -g vercel

# Deploy
vercel --prod
```

## After Deployment:

1. Test all features:
   - [ ] User registration/login
   - [ ] Video upload
   - [ ] Blog creation
   - [ ] Messaging
   - [ ] AI chat
   - [ ] File downloads

2. Monitor logs for errors

3. Set up custom domain (optional)

4. Enable HTTPS (usually automatic)

## Troubleshooting:

- **CORS Errors**: Add your frontend URL to `ALLOWED_ORIGINS` in backend
- **Database Issues**: Check that database file is created and writable
- **File Uploads**: Verify upload directories exist and have permissions
- **Environment Variables**: Double-check all are set correctly

