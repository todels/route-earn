# Route Earn — wireframe

Mid-fidelity wireframe for **Route Earn**: USDG vaults on [route.fun](https://route.fun), powered by Morpho × Steakhouse.
Light mode only. Single static file, no build step.

**Live:** https://todels.github.io/route-earn/  
**Local:** open `index.html` in a browser.

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
├─────────────────────────────┬─┴───────────────────────────┤
│ transaction hist. │ powered by  │  how it works       │
└───────────────────┴─────────────┴─────────────────────┘
```

## Visual hierarchy (in order)

1. **Position value** in USDG. Largest number on the page, inside the tinted "shell" block the swap card uses. Also the withdrawable amount, so it is shown once.
2. **Vault APY**, its own block, second-largest number.
3. **Deposit** (dark CTA) and **Withdraw** (secondary), same button language as `connect wallet` on the swap.
4. **Other USDG vaults** with rating, TVL and APY. Selected vault uses the same green "selected" treatment as a selected route.
5. Net deposited and earnings as a metric row inside the hero.
6. History and provenance (Morpho × Steakhouse) on the bottom row, deliberately smaller.

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
