# Backtesting

Simulate how different alert criteria would have performed on historical data.

## How It Works

Backtesting lets you test different parameters to see what signals would have been generated historically and how they performed.

## Simulation Parameters

**Wallet Selection Criteria:**
- Smart money score thresholds
- Minimum/maximum coins traded
- Average and median gain requirements
- Maximum rug rate and failure rate
- Moon rate thresholds
- Multiplier count requirements (5x, 10x, 20x, 100x)
- Concentration ratio limits
- Recent activity filters
- Exclude copytraders

**Alert Trigger Criteria:**
- Minimum wallet count
- Minimum cumulative score
- Minimum cumulative USD
- Correlation window (time between buys)

## Results

Simulations return:

- Total tokens that would have triggered alerts
- Rug rate of those tokens
- Average and median max gains
- Multiplier distribution (5x, 10x, 20x, 50x, 100x, 500x, 1000x counts)
- Entry market cap statistics
- Full list of tokens with details

## Correlation Analysis

The correlations endpoint analyzes which wallet metrics best predict token outcomes, showing:

- Correlation with max gain
- Correlation with above-median performance
- Ranked by predictive power
