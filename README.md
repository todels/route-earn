# Route Earn — wireframe

Mid-fidelity wireframe for **Route Earn**: USDG vaults on [route.fun](https://route.fun), powered by Morpho × Steakhouse.
Light mode only. Single static file, no build step.

**Open:** `index.html` in a browser (or serve the folder with any static server).

## Screens

| # | Screen | What it answers |
|---|--------|-----------------|
| 01 | Earn overview | "How much do I have, how is it doing, what can I do?" |
| 02 | Deposit | "What am I putting in, what do I get, what changes for me?" |
| 03 | Empty state | "Why should I deposit, and where?" |

## Layout

The page keeps Route's existing frame: top band (theme toggle / nav pills / wallet), a middle band, and a bottom band (docs, twitter, stats). The middle band is a 12-column bento instead of the swap's 3 fixed columns.

```
┌───────────────────────────┬─────────────┬─────────────┐
│                           │  vault APY  │  available  │
│   your position (hero)    ├─────────────┴─────────────┤
│   value · deposited ·     │  USDG vaults (Steakhouse) │
│   earnings · APY · CTAs   │  Prime / High Yield / Term│
├───────────────────┬───────┴─────┬─────────────────────┤
│ transaction hist. │ powered by  │  how it works       │
└───────────────────┴─────────────┴─────────────────────┘
```

## Visual hierarchy (in order)

1. **Position value** in USDG. Largest number on the page, inside the tinted "shell" block that the swap card uses.
2. **Net deposited / earnings / current APY** as a metric row inside the hero.
3. **Deposit** (dark CTA) and **Withdraw** (secondary), same button language as `connect wallet` on the swap.
4. **Vault APY** and **available to withdraw** as their own blocks, so they can be scanned without reading the hero.
5. **Vault list** with rating, TVL and APY. Selected vault uses the same green "selected" treatment as a selected route.
6. **History, provenance, explainer** on the bottom row.

## Brief coverage

| Requirement | Where |
|-------------|-------|
| Current position value in USDG | Hero, 56px number |
| Net deposited amount | Hero metric 1 |
| Earnings / loss, when reliable | Hero metric 2; shows a `calculating` chip until it can be computed |
| Current variable APY | Hero metric 3 + dedicated APY block with 7d / 30d and sparkline |
| Amount available to withdraw | Dedicated block with liquidity bar |
| Deposit and withdraw buttons | Hero button row; deposit flow in screen 02 |
| Transaction history | Bottom-left block with type / date / amount / position after / tx |

## Design tokens

Pulled from route.fun light mode: `#f7f7f2` ground, `#252620` ink, `#567b51` accent, `#eff4ec` selected, 8px block radius, 24px inner cards, Geist.
