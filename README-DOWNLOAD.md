# Deen Time - Islamic Prayer Companion App

## Download Instructions

Your Islamic prayer companion app is ready for download! Here's how to get it:

### Option 1: Download from Replit (Recommended)
1. Click the three dots menu (⋮) at the top of your Replit project
2. Select "Download as zip"
3. Extract the downloaded file on your computer

### Option 2: Clone from Git (if you have Git installed)
```bash
git clone https://replit.com/@username/your-repl-name
```

## Running the App Locally

After downloading, follow these steps to run your app:

### Prerequisites
- Node.js (version 18 or higher)
- PostgreSQL database

### Installation Steps

1. **Extract and navigate to the project folder:**
```bash
cd deen-time-app
```

2. **Install dependencies:**
```bash
npm install
```

3. **Set up your database:**
   - Create a PostgreSQL database
   - Set the DATABASE_URL environment variable
   - Run database migrations:
```bash
npm run db:push
```

4. **Set up environment variables:**
   Create a `.env` file in the root directory with:
```
DATABASE_URL=your_postgresql_connection_string
VITE_OPENCAGE_API_KEY=your_opencage_api_key
```

5. **Start the development server:**
```bash
npm run dev
```

6. **Open your browser and visit:**
   `http://localhost:5000`

## Features Included

✅ **Prayer Times** - Location-based accurate Islamic prayer times
✅ **Ramadan Countdown** - Live countdown to next Ramadan
✅ **Prayer Tracking** - Track your daily prayers with streak counter
✅ **Quran Reader** - Embedded Quran.com for reading
✅ **Friday Prayers** - Dedicated Jummah prayer information
✅ **Hadith Section** - Daily authentic hadith
✅ **Duas Collection** - Islamic supplications
✅ **Masjid Finder** - Interactive map to find nearby mosques
✅ **Islamic Calendar** - Hijri date conversion
✅ **Events Management** - Community event tracking

## Technology Stack
- **Frontend**: React 18, TypeScript, Tailwind CSS
- **Backend**: Node.js, Express
- **Database**: PostgreSQL with Drizzle ORM
- **Build Tool**: Vite
- **UI Components**: Radix UI with Shadcn/ui

## Support
If you need help setting up or have questions, feel free to ask!

---
*May this app help you stay connected with your faith. Barakallahu feeki!*