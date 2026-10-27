# NHP Live Typing

A simple two-person real-time typing room, without user accounts. Both participants must know the same long room code.

## Run on a computer
1. Install Node.js 18 or newer.
2. Open a terminal in this folder and run `npm install`.
3. Run `npm start`.
4. Open `http://localhost:3000`.

## Use from two different networks
Deploy this entire project to a Node.js hosting service supporting persistent WebSocket connections (e.g. Render Web Service). Connect a GitHub repository, choose Node, build command `npm install`, start command `npm start`, and deploy. Open the resulting HTTPS URL on both phones. On the first phone press Generate Code, share that code with the second phone, and join the same room on both phones.

Note: The static HTML file alone cannot sync phones; server.js must be running. Some free hosting services sleep when idle and may disconnect users. The server stores room text in memory only; a restart clears it.

## Security limitations
The room code acts as a shared secret, not a verified identity. Anyone with the code can join if a slot is open. There is no end-to-end encryption, rate limiting, persistent storage, or strong access control. Avoid confidential data. Use HTTPS hosting. The server relays live text and keeps it temporarily in memory until the room is empty or the server restarts.
