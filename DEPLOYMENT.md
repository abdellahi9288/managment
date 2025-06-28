# Deployment Guide for Vercel

## Prerequisites
- Vercel account
- GitHub repository connected to Vercel

## Step 1: Deploy Backend First

1. **Create a new Vercel project for the backend:**
   - Go to [vercel.com](https://vercel.com)
   - Click "New Project"
   - Import your GitHub repository
   - Set the following configuration:
     - **Framework Preset:** Node.js
     - **Root Directory:** `server`
     - **Build Command:** `npm run build`
     - **Output Directory:** `dist`
     - **Install Command:** `npm install`

2. **Set Environment Variables in Vercel:**
   - Go to your project settings
   - Add these environment variables:
     ```
     NODE_ENV=production
     PORT=3000
     DATABASE_URL=your_mongodb_atlas_url
     JWT_SECRET=your_jwt_secret_key
     ```

3. **Deploy the backend**

## Step 2: Deploy Frontend

1. **Create another Vercel project for the frontend:**
   - Click "New Project" again
   - Import the same GitHub repository
   - Set the following configuration:
     - **Framework Preset:** Vite
     - **Root Directory:** `client`
     - **Build Command:** `npm run build`
     - **Output Directory:** `dist`
     - **Install Command:** `npm install`

2. **Set Environment Variables:**
   - Add this environment variable:
     ```
     VITE_BASE_URL=https://your-backend-vercel-url.vercel.app/api/v1
     ```

3. **Deploy the frontend**

## Alternative: Deploy as Monorepo

If you want to deploy everything together:

1. **Use the root vercel.json configuration**
2. **Set all environment variables in one project**
3. **Deploy the entire repository**

## Environment Variables Needed

### Backend (.env)
```
NODE_ENV=production
PORT=3000
DATABASE_URL=mongodb+srv://username:password@cluster.mongodb.net/inventory-management
JWT_SECRET=your_secure_jwt_secret_here
```

### Frontend (.env)
```
VITE_BASE_URL=https://your-backend-url.vercel.app/api/v1
```

## Database Setup

1. **Create MongoDB Atlas cluster**
2. **Get connection string**
3. **Add to environment variables**

## Troubleshooting

- **Build errors:** Check Node.js version (use 18.x)
- **API errors:** Verify environment variables
- **CORS errors:** Ensure backend URL is correct in frontend
- **Database errors:** Check MongoDB connection string

## URLs After Deployment

- **Frontend:** `https://your-frontend-project.vercel.app`
- **Backend:** `https://your-backend-project.vercel.app`
- **API:** `https://your-backend-project.vercel.app/api/v1` 