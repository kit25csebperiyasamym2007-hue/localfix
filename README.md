# LOCALFIX
Vite + Supabase (auth, Postgres, Realtime) + Leaflet/OpenStreetMap. Only Supabase needs keys.

## Run locally
    npm install && cp .env.example .env   # fill in the two Supabase values
    npm run dev
Leave `.env` empty for offline demo mode (OTP 1234, mock data).

## Supabase setup
1. Create a project, then run `supabase/schema.sql` in the SQL Editor.
2. Authentication → Providers → Phone: enable and connect an SMS provider (e.g. Twilio). For testing, add test numbers with fixed OTPs.
3. Settings → API: copy the Project URL and anon key.

## Deploy to Vercel
Push to GitHub → Vercel → Import → add env vars `VITE_SUPABASE_URL` and `VITE_SUPABASE_ANON_KEY` → Deploy.

## Real-time features
Provider online/offline, new booking requests, booking status, chat, and worker GPS (Supabase Broadcast → Leaflet map).
Test with two browsers: customer in one; in the other, log in and use Profile → Provider mode → register, then set an admin to verify.
