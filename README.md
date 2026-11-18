# Breach Zero online

One Node process serves the game page and relays live rooms. Anyone who opens the URL can host or join rooms.

## Run locally
    npm install
    npm start          # http://localhost:3000

## Put it online (no Claude, no sign-in for players)
1. Push this folder (index.html, server.js, package.json) to a GitHub repo.
2. Create a Web Service from that repo on Render, Railway or Fly.io. Build: `npm install`. Start: `npm start`. Health check: `/health`.
3. You get an https:// URL. Players open it on any computer or phone and use Host / Join.
4. Optional: add a custom domain in the host's dashboard so the address is easy to type.

Notes
- Free tiers usually sleep when idle, so the first visit can take about a minute. A paid instance or a ping to /health every few minutes keeps it awake.
- The server only relays room state. The room creator's browser runs the bots and round logic, so a match ends if its creator leaves.
- Clients are trusted (no anti-cheat, no accounts).
