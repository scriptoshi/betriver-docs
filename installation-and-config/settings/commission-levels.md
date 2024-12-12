---
description: User Levels Configuration Guide
icon: objects-column
---

# Commission Levels

<figure><img src="../../.gitbook/assets/Commission fees.jpg" alt="" width="375"><figcaption></figcaption></figure>

***

####

Each user level has specific limits, fees, and commission settings that can be customized to match your platform's policies.

**Overview of Levels**

There are three user levels available which can name as you wish.

1. **Level One**: This is the default level for new users.
2. **Level Two** Offers higher limits and reduced fees for experienced users.
3. **Level Three**: Designed for high-volume users with the most favorable terms.

***

#### Configuration Fields

**1. Level Name**

The name of the user level. For instance, "Standard," "Intermediate," or "Pro."

**2. Level Description**

A brief description of the level. Use placeholders such as `:commissionProfit` or `:exchangeMaxBet` to dynamically display settings.

**3. Limits Guide**

A text description outlining specific limits, such as maximum bets or transactions per calendar month.

**4. Opt-in (Join) Fees**

A one-time fee users must pay to join this level. Enter `0` for no opt-in fees.

**5. Deposit Limits**

* **Max Daily Deposit**: The maximum amount a user can deposit in a single day.
* **Max Monthly Deposit**: The maximum cumulative deposit allowed per month.

**6. Betting Limits**

* **Min Exchange Bet**: The smallest bet amount allowed in the exchange.
* **Max Exchange Bet**: The largest bet amount allowed in the exchange.
* **Min Bookie Bet**: The smallest bet amount allowed in the bookie section.
* **Max Bookie Bet**: The largest bet amount allowed in the bookie section.

**7. Commissions**

* **Commission on Bet**: A percentage charged on each bet placed.
* **Commission on Profit**: A percentage charged on net profits. For example, a value of `1%` applies to the net profit earned by the user.

**8. Transaction Fees**

* **Deposit Fees**: A percentage fee applied to each deposit transaction.
* **Withdraw Fees**: A percentage fee applied to each withdrawal transaction.

***

#### Example: Level One (Standard)

| **Field**                | **Value**                                                              |
| ------------------------ | ---------------------------------------------------------------------- |
| **Level Name**           | Standard                                                               |
| **Level Description**    | You pay `:commissionProfit` % commission on net profit per market only |
| **Limits Guide**         | Max `:exchangeMaxBet` bets placed per calendar month                   |
| **Opt-in Fees**          | $0                                                                     |
| **Max Daily Deposit**    | $1,000                                                                 |
| **Max Monthly Deposit**  | $5,000                                                                 |
| **Min Exchange Bet**     | $1                                                                     |
| **Max Exchange Bet**     | $1,000                                                                 |
| **Min Bookie Bet**       | $1                                                                     |
| **Max Bookie Bet**       | $100                                                                   |
| **Commission on Bet**    | 0%                                                                     |
| **Commission on Profit** | 1%                                                                     |
| **Deposit Fees**         | 1%                                                                     |
| **Withdraw Fees**        | 1%                                                                     |

***

#### Updating Settings

1. Navigate to the **Commission Settings** page in the admin dashboard.
2. Select the user level you wish to edit.
3. Modify the fields as needed.
4. Click **Update Settings** to save changes.

***

#### Tips for Configuration

* Use realistic limits to cater to the needs of each user tier.
* Ensure commission and fees are competitive while maintaining profitability.
* Regularly review and adjust settings based on user activity and feedback.

***

