---
sidebar_label: "JLP Pool"
title: "JLP Pool"
description: How to Become Liquidity Provider
---

Users can become Liquidity Providers (LPs) by allocating their assets or tokens into the Jupiter Liquidity Provider Pool (JLP Pool) and in return, you will get the JLP token. The JLP pool receives 70% of the fees. So, as a JLP holder, the increase of the underlying value of the the JLP pool means that your JLP token price increases.

JLP token is also a SPL token. So, it can be transferred like any SPL tokens. AMM pools can also be set up for trading JLP token as well.

### JLP, Liquidity Provider Token

JLP, or the Liquidity Provider token, represents a meticulously constructed index of assets designed for swaps and leverage trading. These tokens can be created using any index asset and later redeemed for any index asset.

Liquidity providers serve a crucial role as they act as counterparty to traders. When traders seek to open leverage positions, they borrow tokens from the pool. Liquidity providers, in return, earn fees from these leverage trading activities, along with borrowing fees and earnings from swaps. As a JLP holder, you receive 70% of the fees generated by the trading exchange. This amount is directly reinvested into the JLP, increasing the price of JLP, facilitating continuous compounding of yield and earnings. The exchange generates fees and yield in three ways:

- Opening and Closing Fees of Positions
- Borrowing Fees of Positions
- Trading Fees of the Pool

The fees are being compounded into the pool hourly.

:::info Overall Yield Calculation
It is essential to note that pool earnings and losses (index token appreciation/depreciation) are not factored in the overall yield calculation.
:::

### Risks Associated with Holding JLP

Now, let's explore some of the risks associated with holding JLP:

**Profit and Loss (P&L) Dynamics:** Traders' P&L from perpetual trading impacts the JLP pool. If a trader incurs a net positive P&L, the losses are sourced from the JLP pool to compensate the trader. Conversely, if a trader's P&L is net negative, the gains are deposited into the JLP pool for LP holders.

**Impermanent Loss:** The JLP pool consists of both stable and non-stable tokens. Fluctuations in token prices can affect the value of JLP. As a result, users may find that their withdrawn tokens are worth less compared to their initial deposit. Additionally, deposit and withdrawal fees for the JLP Pool may further reduce the number of tokens withdrawn, particularly for shorter holding periods.

### Adding/Removing Liquidity

When an LP adds liquidity to the JLP pool, they increase the amount of liquidity in the total TVL (Total value lock) which increase the amount tradable on the trading side.

Liquidity providers (LPs) may use any token to deposit into one of the pool's custody. We will use Jupiter Swap to swap the LP's token into the custody's token.

Similarly when withdrawing from a custody, LPs may request to receive a different token than the custody's token. We will use Jupiter Swap to swap the custody's token to the LP's desired token.

And at the point of depositing assets into JLP pool, the protocol will price in the USD value.

#### How to Add Liquidity to JLP:

1. Begin by selecting the token asset you wish to deposit into the JLP pool from the list of token assets available in your wallet.
2. JLP Pool will automatically identify which token asset in the JLP pool has the lowest weightage and swap your selected asset into that pool (if your chosen output token is not in the list of token assets). Your assets will then be deposited into the pool.
3. Keep in mind that when you deposit into the JLP pool with a relatively high weightage, fees will be incurred. Conversely, depositing into a token pool with lower weightage will result in lower or even zero fees during the deposit process.
4. For instance, if users deposit a token asset that is not in the pool (e.g., SOL, ETH, BTC, USDC, or USDT), swap will be executed into the token asset with the lowest weightage, ensuring minimal fees.

![JLP1](../img/jlp1.jpg)

#### How to Remove Liquidity from JLP:

1. Start by selecting the token asset you intend to withdraw from the JLP pool. You can choose from the list of available token assets in the pool, and the chosen asset will be withdrawn directly into your wallet.
2. JLP Pool will automatically identify the token asset in the JLP pool with the highest weightage and swap your chosen asset into that pool if your selected output token is not in the list of token assets. Your assets will then be withdrawn directly into your wallet.
3. It's important to note that when you withdraw from the JLP token pool with a relatively low weightage, fees will be incurred. Conversely, withdrawing from a token pool with higher weightage will result in lower or even zero fees during the withdrawal process.
4. In situations where users are withdrawing a token asset not present in the pool (e.g., SOL, ETH, BTC, USDC, or USDT), JLP will withdraw from the token pool with the highest weightage, incurring minimal fees. The withdrawn assets will be swapped into the selected output token and then transferred directly into the user's wallet.

![JLP2](../img/jlp2.jpg)

### Target Ratio and Fees

In the JLP pool, every token has a specific target ratio or weightage.

The transactions involving the addition or removal of liquidity have the primary purpose of adjusting a token's ratio in the pool to align it more closely with the predefined target.

Instructions that move the token's ratio away from the target incurs additional fees while instructions that move it closer to the target get a fee discount.

### Fee Calculations

| Action | Fee |
|---|---|
| Opening a Position | 10 BPS |
| Closing a Position | 10 BPS |
| Swap Fee | Between 0 BPS to 200 BPS depending on pool weightage |
| Borrow Rate | 1 BPS/hour x token utilization percentage |

Fee calculation for opening and closing positions involves the volume of these transactions, multiplied by the fee percentage of 0.1%.

The borrow fee, often termed as the hourly borrow fee, is computed as follows:

```
hourly borrow fee = (tokens borrowed / tokens in the pool) x 0.01% x position size
```

Trade fees for the pool typically range between 0% and 2%.

### Example Yield

To provide an estimated perspective, you can calculate potential revenue by taking Jupiter perpetual exchange's daily or weekly total volume and multiplying it by a fee percentage. For instance:

* Total Daily Volume: 50 million
* Fee Percentage: 0.1%
* Revenue Share Percentage: 70%

Using these values, the calculation would be as follows:

Total revenue to be shared between JLP pool holders:

```
$50M x 0.1% x 70% = $35,000
```

To determine your specific share or weight in the total JLP pool, use the following formula:

```
your_pool_contributed_amount / total_pool_amount x 100 = your_pool_percentage
```

For example:

* Your contribution: $1,000
* Total pool amount: $4,000,000
* Your share percentage: 1,000 / 4,000,000 x 100 = 0.025%

Finally, you can calculate your generated revenue share by multiplying the results of the first and second calculations:

```
revenue share you generate = $35,000 x 0.025% = $8.75
```
