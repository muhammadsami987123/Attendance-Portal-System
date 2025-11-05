# Setting Up MongoDB on Vercel

## The Problem
Your `.env.local` file works locally, but Vercel doesn't have access to it. You need to add environment variables in Vercel's dashboard.

## Solution: Add Environment Variable in Vercel

### Method 1: Via Vercel Dashboard (Recommended)

1. **Go to Vercel Dashboard:**
   - Visit: https://vercel.com
   - Login to your account
   - Select your project: `attendance-portal-system`

2. **Navigate to Settings:**
   - Click on your project
   - Go to **Settings** tab (top navigation)
   - Click **Environment Variables** in the left sidebar

3. **Add MongoDB URI:**
   - Click **"Add New"** button
   - **Name:** `MONGODB_URI`
   - **Value:** `mongodb+srv://msamiwaseem1234_db_user:mlWwgktDO1teVfo5@attendance-portal-syste.npq0h4y.mongodb.net/attendance-portal-system?retryWrites=true&w=majority`
   - **Environment:** Select all three:
     - ✅ Production
     - ✅ Preview  
     - ✅ Development
   - Click **"Save"**

4. **Redeploy:**
   - Go to **Deployments** tab
   - Click the three dots (⋯) on your latest deployment
   - Click **"Redeploy"**
   - Or push a new commit to trigger a new deployment

### Method 2: Via Vercel CLI

Run this command in your terminal:

```bash
vercel env add MONGODB_URI
```

When prompted:
- Enter the connection string: `mongodb+srv://msamiwaseem1234_db_user:mlWwgktDO1teVfo5@attendance-portal-syste.npq0h4y.mongodb.net/attendance-portal-system?retryWrites=true&w=majority`
- Select environments: Production, Preview, Development (type `a` for all)

Then redeploy:
```bash
vercel --prod
```

## Verify It's Working

After adding the environment variable and redeploying:
1. Go to your Vercel deployment URL
2. Try creating an employee
3. If it works, you're all set! ✅

## Security Note
- Never commit `.env.local` to Git (it's already in `.gitignore`)
- Environment variables in Vercel are encrypted and secure
- Only you (and team members with access) can see them

