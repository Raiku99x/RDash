# Hoop Hero Dash – engagement update
- Coin combo (x2–x5) with live meter; bonus score per coin
- Stunts: Clean Jump, Slide Under, Close Call (+score, pop-ups)
- Distance milestones every 250 m, live "NEW BEST!" alert
- Daily missions (3/day, difficulty scales with level, +150 sweep bonus)
- XP + levels (level-up coin rewards)
- Upgrade shop: Magnet, Shield, MVP Fuel, Head Start, Lucky Charm, Coin Bank
- Revive ("Continue?" 5s countdown, costs coins, max 2 per run)
- Mystery chest after every run (common → 800-coin jackpot)
- Daily login streak (7-day cycle)
- Screen shake / red flash / haptics on hit, new sound effects
All progress is saved in localStorage (key: hhprog). All new code lives in the `FX` script block in index.html.

## Buyable heroes
- Rene Bot (5,000 coins) and Water Rene (10,000 coins). Prices: `HERO` constant in the FX script block of index.html.
- Models live in assets/extra_skins.js (loaded before the game; if missing the game still runs with the 3 original heroes).
- Both heroes use the shared run/jump/slide animations (their own 178 built-in animations were stripped to save size).
