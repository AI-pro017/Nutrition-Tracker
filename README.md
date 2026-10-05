# Nutrition Tracker

A small web app for tracking daily nutrition against your own goals.

You decide what to track, like calories, protein or water, and set a target for each one (for example, protein above 120 g or sugar below 30 g). Each day you log your numbers, and the dashboard shows how you're doing over the last week, month, quarter or year.

Live demo: https://tracking-app-indol.vercel.app

## What it does

- Lets you create your own metrics with any unit and edit or remove them later.
- Lets you set a goal per metric as either "more than" or "less than" a target value.
- Has a daily input page for logging values by date.
- Shows a dashboard with a trend chart, your target line, days within target, missed days, your daily average and how far off the target you are.
- Lists your most recent entries with a quick within/missed status.

## Tech stack

- Next.js 15 (App Router) with React 19 and TypeScript
- Tailwind CSS 4
- PostgreSQL on Neon with Drizzle ORM

## Running it locally

You need Node.js 18 or newer and a Postgres database. A free Neon database works fine.

```bash
git clone https://github.com/AI-pro017/Nutrition-Tracker.git
cd Nutrition-Tracker
npm install
```

Copy the example env file and put your connection string in it:

```bash
cp .env.example .env.local
```

Create the tables, then start the dev server:

```bash
npx drizzle-kit push
npm run dev
```

The app runs at http://localhost:3000. Start on the Metrics page, add a goal, and then log a few days of data to fill the dashboard.

## Project structure

```
src/
  app/
    api/            API routes for metrics, goals and daily entries
    daily-input/    Page for logging daily values
    goals/          Page for setting targets
    metrics/        Page for managing metrics
    page.tsx        Dashboard
  components/       Navigation and small UI components
  lib/db/           Drizzle schema and database client
drizzle/            SQL migrations
```
