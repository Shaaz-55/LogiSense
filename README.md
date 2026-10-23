# LogiSense

LogiSense tracks shipments on a live map and scores how likely each one is to be delayed. It also suggests the fastest route for a shipment. It pulls real weather, routing, ship, flight and disaster data instead of using mocked numbers.

**Live demo:** https://logi-sense-sigma.vercel.app

I originally built this for the Google Solution Challenge, then rebuilt the data layer around live APIs.

<!-- Add 1-2 screenshots here, e.g. ![Dashboard](docs/dashboard.png) -->

## What it does

- Shows shipments on a map and tracks their movement
- Suggests the fastest route for a shipment
- Gives each shipment a delay risk score
- Uses live data for weather, roads, ships, flights and disasters

## How the delay score works

The risk score comes from a rule-based engine. It looks at conditions along a shipment's path (for example bad weather, a disaster alert nearby, or a slow route) and combines them into one score. It is not a trained ML model. The rules are simple on purpose so it's easy to see why a shipment got its score.

<!-- Add a short example: which rules fire, and how they add up. -->

## Data sources

| Source | Used for |
| --- | --- |
| [OpenWeatherMap](https://openweathermap.org/) | Weather along the route |
| [OSRM](https://project-osrm.org/) | Road routing and travel times |
| [AISStream](https://aisstream.io/) | Live ship positions |
| [OpenSky](https://opensky-network.org/) | Live flight positions |
| [GDACS](https://www.gdacs.org/) | Global disaster alerts |

## Tech stack

- Vite + TypeScript
- Gemini API <!-- add one line: what Gemini is used for in the app -->
- Deployed on Vercel

## Run locally

You need Node.js.

1. Install dependencies:
   ```
   npm install
   ```
2. Copy `.env.example` to `.env.local` and add your keys. At minimum you need `GEMINI_API_KEY`. <!-- list the other keys (OpenWeatherMap, AISStream) if the app needs them -->
3. Start the app:
   ```
   npm run dev
   ```

## Project structure

```
src/             App source code
index.html       Entry page
vite.config.ts   Vite config
.env.example     Example environment variables
```

## Known issues and next steps

- <!-- Be honest: what's missing or rough? e.g. rate limits on free APIs, scoring rules not tuned against real delay data -->

## Author

Shaaz, https://github.com/Shaaz-55
