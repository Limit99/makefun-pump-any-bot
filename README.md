[![make.fun · u-boothlord-pump-fun-paper-sprint-any-bot-can-f83c389b](https://make.fun/badge/u-boothlord-pump-fun-paper-sprint-any-bot-can-f83c389b.svg)](https://make.fun/bounty/u-boothlord-pump-fun-paper-sprint-any-bot-can-f83c389b?utm_source=github&utm_medium=readme&utm_campaign=u-boothlord-pump-fun-paper-sprint-any-bot-can-f83c389b)
[![rank](https://make.fun/badge/u-boothlord-pump-fun-paper-sprint-any-bot-can-f83c389b/Limit99/makefun-pump-any-bot/rank.svg)](https://make.fun/bounty/u-boothlord-pump-fun-paper-sprint-any-bot-can-f83c389b/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=u-boothlord-pump-fun-paper-sprint-any-bot-can-f83c389b)
[![reward](https://make.fun/badge/u-boothlord-pump-fun-paper-sprint-any-bot-can-f83c389b/Limit99/makefun-pump-any-bot/reward.svg)](https://make.fun/bounty/u-boothlord-pump-fun-paper-sprint-any-bot-can-f83c389b?utm_source=github&utm_medium=readme&utm_campaign=u-boothlord-pump-fun-paper-sprint-any-bot-can-f83c389b)

# Any Bot Can Win — Paper Bot

A paper-trading bot for the make.fun bounty "Pump.fun Paper Sprint: Any Bot Can Win" (harness `agent-fun/replay/v2`, protocol `pumpfun-replay`). It trades pump.fun bonding curves on a replay of real market data with 10 SOL of paper capital, aiming for the highest net PnL on a 6-hour window.

Strategy (`strategy.ts`, original work): selective momentum entries — curves aged at least 800 slots with 5–70 SOL of real reserve, strong net buying inflow over a 30-slot window (≥4 SOL, ≥12 buy trades from ≥10 distinct buyers), price up 8–80% and near its window high, with accelerating flow in the second half of the window. First buys are small (0.03 SOL) with adds up to 0.8 SOL per mint; exits are a tight −10% stop, a 20% trailing stop armed at +10%, a fade exit, and a 900-slot maximum hold. Small 0.011 SOL probe trades, paced to reach 22 distinct coins, cover the guardrail of a round trip of at least 0.01 SOL on at least 20 coins.

`vendor/makefun-bot.ts` is the kit's SDK shim, copied byte-for-byte and excluded from authorship. The bot is deterministic: two executions produce byte-identical action logs.

Run it with: `node main.ts`
