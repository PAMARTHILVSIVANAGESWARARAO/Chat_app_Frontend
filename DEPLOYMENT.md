# Netlify Deployment Guide

## Prerequisites
- Node.js 18+ installed
- Netlify account
- Backend deployed (already at: https://chat-app-backend-nwct.onrender.com)

## Local Setup
1. Install dependencies:
   ```bash
   npm install
   ```

2. Create `.env` file from `.env.example`:
   ```bash
   cp .env.example .env
   ```

3. Update `.env` with your backend URL if different

4. Test locally:
   ```bash
   npm run dev
   ```

## Netlify Deployment Steps

### Option 1: Netlify CLI (Recommended)
1. Install Netlify CLI:
   ```bash
   npm install -g netlify-cli
   ```

2. Login to Netlify:
   ```bash
   netlify login
   ```

3. Initialize site:
   ```bash
   netlify init
   ```

4. Deploy:
   ```bash
   netlify deploy --prod
   ```

### Option 2: Git-based Deployment
1. Push your code to GitHub/GitLab
2. Connect your repository to Netlify
3. Set build settings:
   - Build command: `npm run build`
   - Publish directory: `dist`
   - Node version: `18`

4. Set environment variables in Netlify dashboard:
   - `VITE_BACKEND_URL`: https://chat-app-backend-nwct.onrender.com

### Option 3: Drag & Drop
1. Build the project:
   ```bash
   npm run build
   ```

2. Drag the `dist` folder to Netlify drop zone

## Environment Variables
Set these in Netlify dashboard under Site settings > Environment variables:
- `VITE_BACKEND_URL`: Your backend API URL

## Troubleshooting
- If you get CORS errors, ensure backend allows your Netlify domain
- Check build logs in Netlify dashboard for any build issues
- Ensure Node version is set to 18 in Netlify settings
