# Hugh

A cute colour matching game for two. You get a colour card and mix it from scratch with a colour picker. The closer match wins.

## Modes

- **Colour Duel**: you both get the same card. The closer mix wins the round and hits the other player for the gap between your scores. Damage goes up as the rounds go on (×1.5 from round 3, ×2 from round 5, up to ×3), and a match within ΔE 2 adds a 10 point bullseye bonus. The card can stay up, or flip over after 5 or 2 seconds so you match from memory.
- **Card Swap**: you each make a deck of 3, 5 or 7 named colour cards, then match each other's deck. Highest total wins. In "Name only" the matcher sees just the name, like "inside of a ripe mango".

Closeness is measured with CIEDE2000 (ΔE). A perfect match scores 100, ΔE 5 about 83, ΔE 10 about 63.

## Playing phone to phone

1. Open the site on both phones.
2. One of you taps **Start a room** and types their name. A four-letter code appears.
3. The other taps **Join a room**, types their name and the code.
4. The host picks Colour Duel or Card Swap and taps **Start on both phones**.

The phones find each other through PeerJS's free public broker, using the room code as the host's address, the same way Paddle Draft pairs phones. After that, game moves go straight from phone to phone (WebRTC), so it works on different Wi-Fi networks too. Nothing is stored on a server.

The room is one shared copy of the game. The host's phone keeps it up to date and each phone saves its own copy, so a reload, a locked screen or a closed tab doesn't lose anything. Open Hugh again and it rejoins the same room and carries on: half-made decks, locked-in picks and hearts are all kept. Tap the room pill at the top for the menu (back to the game, end the game, leave the room).

You can also play on one phone (pass and play), or send each other decks as codes by text message.

## Files

- `index.html` – the whole game.
- `vendor/peerjs.min.js` – PeerJS 1.5.5 (MIT, see `vendor/LICENSE-peerjs`).
