# Mark Benefits App - Setup Guide

## Quick Start

### 1. Install Dependencies
```bash
npm install
```

### 2. Configure API Key (Required for Chatbot)

The AI chatbot requires an Anthropic API key:

1. Get your API key from: https://console.anthropic.com/
2. Copy `.env.example` to `.env`:
   ```bash
   cp .env.example .env
   ```
3. Add your API key to `.env`:
   ```
   ANTHROPIC_API_KEY=your_actual_api_key_here
   ```

### 3. Run Locally

#### Option A: Full Stack (Recommended - With API Support)
```bash
npm run dev
```
This runs both:
- React app at http://localhost:3000
- API server at http://localhost:3001

✅ All features work including AI chatbot (if API key is configured)

#### Option B: Frontend Only
```bash
npm start
```
This runs just the React app at http://localhost:3000
- ✅ All calculators and tools work
- ⚠️ AI chatbot shows a setup message

### 4. Build for Production
```bash
npm run build
```

## Features Available

### Without API Key:
✅ Landing Page
✅ Benefits Cost Analyzer
✅ Market Comparison Calculator
✅ Budget Forecast Tool
✅ RFP Generator
✅ Enrollment Timeline
✅ Medicare Transition Calculator

### With API Key:
✅ All of the above
✅ AI Chatbot (Ask Mark)

## Deployment

### Deploy to Vercel (Recommended)
1. Push code to GitHub
2. Connect repository to Vercel
3. Add `ANTHROPIC_API_KEY` in Vercel project settings
4. Deploy!

## Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `ANTHROPIC_API_KEY` | Optional | Required for AI chatbot feature |

## Troubleshooting

**Q: Chatbot not responding?**
- Make sure you're running with `npm run dev` (not just `npm start`)
- Check that `ANTHROPIC_API_KEY` is set in `.env` file
- Verify the API key is valid at https://console.anthropic.com/
- Check that the API server is running on port 3001

**Q: Build warnings about missing dependencies?**
- Run `npm install` again
- Check that all dependencies in package.json are installed

**Q: Styles not loading?**
- Verify `tailwind.config.js` and `postcss.config.js` exist in root
- Try `npm run build` to test production build
