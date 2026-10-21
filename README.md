# UniSwapPool · Constant-Product AMM Lab

**Explore how a pool turns reserves into prices, and why the size of a trade changes its execution price.**

The [Uniswap V2 lab notebook](uniswap_v2_lab_task.ipynb) develops a Python model of a constant-product automated market maker. It connects the invariant `x × y = k` to swaps, price impact and liquidity provision through code, plots and exercises.

## Inside the notebook

1. **Pool mechanics:** reserve balances, spot price, fees in basis points and amount-out calculations.
2. **Swaps:** update both reserves and inspect the effect on the constant product when fees remain in the pool.
3. **Price impact:** compare marginal price with average execution price as trade size increases.
4. **Liquidity provision:** track pool shares and investigate fee accrual and LP outcomes.
5. **Further experiments:** change reserve depth, trade sequences and fee assumptions.

The notebook mixes implemented reference methods with exercise cells and TODOs. It is a guided lab, so some sections require completion before a full sequential run succeeds.

## Run locally

Requires Python 3.10 or newer, NumPy, Matplotlib and a Jupyter environment.

```bash
python -m pip install jupyterlab numpy matplotlib
python -m jupyter lab
```

Open `uniswap_v2_lab_task.ipynb`. Follow the task order and inspect each reserve update before moving to the visualization sections.

## What to pay attention to

The quoted spot price is not the average price of a finite swap. Fees affect the effective input used in the amount-out formula, while the deposited input changes the actual reserve balance. Those distinctions explain why the invariant behaves differently with and without fees.

The example token balances are simulated. This repository contains no deployed Solidity contracts or live-pool integration; it does not require a wallet, gas payment or real token transfer. Floating-point arithmetic and simplified LP accounting make it an educational model rather than an exact replica of on-chain integer arithmetic.
