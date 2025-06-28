# MongoDB Atlas Setup for Deployment

## Step 1: Create MongoDB Atlas Account
1. Go to [mongodb.com/atlas](https://mongodb.com/atlas)
2. Sign up for a free account
3. Create a new cluster (M0 Free tier is sufficient)

## Step 2: Get Connection String
1. Click "Connect" on your cluster
2. Choose "Connect your application"
3. Copy the connection string
4. Replace `<password>` with your database password
5. Replace `<dbname>` with `inventory-management`

## Step 3: Example Connection String
```
mongodb+srv://username:password@cluster.mongodb.net/inventory-management?retryWrites=true&w=majority
```

## Step 4: Add to Vercel Environment Variables
- Go to your Vercel project settings
- Add environment variable: `DATABASE_URL`
- Paste your connection string

## Step 5: Test Connection
The app will automatically create the database and collections when it first connects. 