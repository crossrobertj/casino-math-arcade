# Casino Math Arcade

Play credits only, no real money. Play a few rounds, then fast-forward thousands and watch luck turn into math.

File: `casino-math-arcade.html` — single self-contained page (no build step, no dependencies except Google Fonts). Open it directly in a browser.

vibecoded by Robert James Cross

## Games

| Game | What you bet on | House edge (default) |
|---|---|---|
| Coin Flip | Heads / Tails, win pays 0.95 to 1 | 2.50% |
| Roulette (European) | Red, black, odd/even, low/high, dozens, single number | 2.70% |
| Dice (craps style) | Pass line, Any seven, Snake eyes, Any craps, Eleven | 1.41% / 11–17% depending on bet |
| Slots | 3-reel, configurable weights and payouts | 7.24% (Normal preset) |
| Blackjack | Hit / stand / double, perfect-play hint + strategy chart | ~1.09% (3:2), ~2.44% (6:5) |
| Texas Hold'em Showdown | Ante vs dealer + optional pocket-pair side bet, configurable rake | 2.40% (5% rake, no side bet) |

Each game panel has a collapsed "How the math works" section with the exact probability, expected value, and fair-payout comparison.

## Use it

- Pick a game with the tabs (`1–6` also works).
- Pick a bet size with the chips (`B` cycles sizes).
- Play one round with the big button (`Space` when the stage is focused).
- Fast-forward 10 / 100 / 1,000 / 100,000 rounds to see the law of large numbers.
- Watch "Luck vs. math": pink = your actual return, gold dashed = expected return, shaded band = 95% luck zone.

Keyboard: `1–6` switch games, `Space`/`Enter` plays, `B` changes bet, `←`/`→` moves tabs.

## Notable controls

- Toolbar: bankroll (starts at 1,000, tracks total net across all games), save status, Auto/Light/Dark theme, Expand/Collapse math, Export CSV, `? Keys` help.
- Blackjack: 3 to 2 vs 6 to 5 payout toggle, "Show the best move" hint with per-move EV.
- Slots: Loose (98.9%) / Normal (92.8%) / Tight (84.2%) presets, or edit weights and payouts directly — RTP and edge update live.
- Hold'em: 0% / 5% / 10% rake plus optional pocket-pair side bet (15 to 1).
- Scoreboard: all games side by side, best edge marked ★, sortable by inspection; CSV export downloads the table.
- Stats persist in `localStorage` (`casino-math-arcade-v2`); resets ask for confirmation.

## Math notes

- Expected value is quoted per credit bet (per starting bet for blackjack, per total wager for Hold'em side-bet mode).
- Blackjack engine assumes an infinite deck, dealer stands on 17, double on any first two, no splits, dealer checks for blackjack first. Fast-forward always plays perfectly; your mistakes are tracked as EV cost.
- Hold'em showdown: both hands random, ties ~4.06%; edge comes only from rake/side bet.
- Chart x-axis is log scale (1, 10, 100, … rounds); y-axis is return (100% = break even).
