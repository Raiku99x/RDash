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
- Rene Bot (10,000 coins) and Water Rene (15,000 coins). Prices: `HERO` constant in the FX script block of index.html.
- Models live in assets/extra_skins.js (loaded before the game; if missing the game still runs with the 3 original heroes).
- Both heroes use the shared run/jump/slide animations (their own 178 built-in animations were stripped to save size).
- Models are the creator's own exports (renebotanim.glb = Rene Bot, exported-model (1).glb = Water Rene), full-res base-colour maps. Materials are tuned (low metalness + slight emissive) so they no longer render dark/gray.
- Water Rene has water particle effects: spiralling spray + mist in the menu and in-run, foot splashes while running, slide spray, and take-off/landing bursts (`waterFX` in index.html).
- Fixed: jumping while on a bus ramp no longer causes Game Over (the rising ramp now carries the player).

## Audio update
- Boss battle music: assets/boss1.mp3 (audio_keeper-boss-battle) and assets/boss2.mp3 (bouncyrunner-boss-fight-one), alternating per boss. Crossfades with the normal BGM when a boss appears, and back when it is defeated / you die. Volume: `BOSS_VOL` in the first script block.
- New synthesized sounds: hero ball throw (`throw`), ball hitting boss (`bhit`), boss shot (`bfire`), boss attack wind-up/roar with a different voice per boss (`bwind`: dragon, fish, spider, snake).
- Death / game-over sound is now decoded into memory (WebAudio) on the first tap and played from there, with the old <audio> element as a fallback. Audio elements are silently "unlocked" on the first tap so mobile browsers don't block them later.
