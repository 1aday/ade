# ADE Artist Scraper - Next.js + shadcn/ui

A powerful web scraper for Amsterdam Dance Event (ADE) artists with real-time progress tracking, database sync, and beautiful dark theme UI.

## 🌟 Features

### Core Features
- 🎯 **ADE API Scraper** - Fetch all artists from Amsterdam Dance Event
- 📊 **Real-time Progress Tracking** - Beautiful animated progress UI
- 💾 **Supabase Integration** - Store and manage artists in PostgreSQL
- 🔄 **Smart Sync** - Detect new artists and update existing ones
- 📈 **Statistics Dashboard** - View total artists, countries, and trends
- 🎨 **Custom Dark Theme** - Beautiful TweakCN dark theme
- 🔍 **Search & Filter** - Find artists quickly
- 📅 **Sync History** - Track all sync operations
- ⚡ **Pagination Support** - Efficiently handle large datasets

### Technical Stack
- ⚡ **Next.js 15** with App Router
- 🎨 **shadcn/ui** component library
- 🌙 **Dark Mode Only** with custom TweakCN theme
- 💅 **Tailwind CSS** for styling
- 📦 **TypeScript** for type safety
- 🗄️ **Supabase** for database
- 🎭 **Framer Motion** for animations
- 📊 **Recharts** for data visualization

## 🚀 Getting Started

### Prerequisites
- Node.js 18+ installed
- Supabase account (free tier works)

### Installation

1. **Clone the repository**
```bash
git clone [your-repo-url]
cd ade
```

2. **Install dependencies**
```bash
npm install
```

3. **Set up Supabase**

   a. Create a new Supabase project at [supabase.com](https://supabase.com)
   
   b. Go to SQL Editor in your Supabase dashboard
   
   c. Run the SQL schema from `supabase/schema.sql`
   
   d. Get your project credentials:
      - Go to Settings → API
      - Copy your Project URL and anon public key

4. **Configure environment variables**

   Create a `.env.local` file:
```env
NEXT_PUBLIC_SUPABASE_URL=your_supabase_project_url
NEXT_PUBLIC_SUPABASE_ANON_KEY=your_supabase_anon_key
```

5. **Run the development server**
```bash
npm run dev
```

6. **Open the application**
   - Homepage: [http://localhost:3000](http://localhost:3000)
   - ADE Scraper: [http://localhost:3000/scraper](http://localhost:3000/scraper)

## 📱 Using the ADE Scraper

### First Time Setup
1. Navigate to `/scraper`
2. Click "Start Sync" to begin fetching artists
3. Watch the beautiful progress tracking in real-time
4. View fetched artists in the Artists tab

### Features Overview

#### Sync Controls
- **Custom Date Range**: Specify which ADE dates to scrape
- **Daily Auto Sync**: Enable automatic daily synchronization (requires deployment)
- **Real-time Progress**: See pages being fetched and processed
- **Statistics**: View total artists, new additions, and countries

#### Progress Tracking
- Live page counter
- Items fetched, new, and updated counts
- Current batch preview
- Status indicators with animations

#### Artist Database
- Search artists by name
- View artist details and countries
- See when each artist was first discovered
- Direct links to ADE profiles

#### Sync History
- Track all sync operations
- See success/failure status
- View items fetched and added
- Error reporting

## 🗄️ Database Schema

The application uses the following main tables:

- **artists** - Stores all artist information
- **sync_history** - Tracks sync operations
- **artist_changes** - Logs all changes to artists
- **events** - For future event storage
- **artist_events** - Links artists to events

## 🛠️ Development

### Project Structure
```
/app
  /scraper        - ADE scraper dashboard
  page.tsx        - Homepage with theme showcase
/components
  /ui             - shadcn/ui components
  sync-progress-card.tsx
  statistics-card.tsx
  artist-list.tsx
  sync-history.tsx
/lib
  ade-api.ts      - ADE API integration
  db-service.ts   - Database operations
  supabase.ts     - Supabase client
  types.ts        - TypeScript definitions
/hooks
  use-ade-sync.ts - Sync logic hook
/supabase
  schema.sql      - Database schema
```

### Adding New Features

To add more shadcn/ui components:
```bash
npx shadcn@latest add [component-name]
```

### API Endpoints

The scraper uses the ADE API:
- Base URL: `https://www.amsterdam-dance-event.nl/api`
- Artists endpoint: `/program/filter/`
- Parameters: `section=persons`, `type=8262,8263`, date range, page

## 🚢 Deployment

### Vercel Deployment
1. Push your code to GitHub
2. Import project in Vercel
3. Add environment variables
4. Deploy

### Daily Sync Setup
For production, consider:
- Vercel Cron Jobs
- GitHub Actions
- External cron service
- Supabase Edge Functions

## 🔒 Security Notes

- The application uses Supabase Row Level Security (RLS)
- API calls include browser headers to avoid blocking
- Rate limiting is implemented (500ms between requests)
- Database credentials are kept in environment variables

## 📝 License

MIT

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## 📚 Learn More

- [Next.js Documentation](https://nextjs.org/docs)
- [shadcn/ui Documentation](https://ui.shadcn.com)
- [Supabase Documentation](https://supabase.com/docs)
- [TweakCN Themes](https://tweakcn.com)
- [Amsterdam Dance Event](https://www.amsterdam-dance-event.nl)