# 📈 Outsmarting the Market: A Rule-Based Dynamic SIP Strategy

Welcome to this repo that explores a **disciplined, rule-based investment strategy** that outperforms traditional SIP (Systematic Investment Plan) by dynamically adjusting investments based on NIFTY's P/E ratio.

> 💡 **Can you beat the market without emotions, predictions, or timing?**  
> Turns out — yes, with a little logic and discipline.

---

## 📊 What's Inside?

- 📄 **Dynamic_SIP_Strategy.docx** — The storytelling article explaining the rationale, method, and insights from the strategy.
- 📓 **PE SIP.ipynb** — Jupyter Notebook with code to:
  - Backtest the dynamic SIP strategy (2000–2025)
  - Calculate XIRR (internal rate of return) over multiple 6-year rolling periods
  - Compare it to a normal SIP approach
  - Analyze results, visualize portfolio growth, and show distribution of performance improvements
- 📂 **results.csv** — Stores all XIRR and portfolio value comparisons across different simulation start dates.
- 📈 **NIFTY Data** — Price and P/E ratio datasets used for the backtest:
  - `NIFTY 50_Historical_PR_01011990to23032025.csv`
  - `NIFTY 50_Historical_PE_PB_DIV_Data_01011996to23032025.csv`

---

## 🔁 Strategy at a Glance

This isn’t just a smarter SIP — it's a **disciplined, rule-based approach**.

### 🔧 Multiplier Rule:

```python
def get_multiplier(pe, avg_pe):
    if pe < 0.85 * avg_pe:
        return 5
    elif pe < 0.925 * avg_pe:
        return 2.5
    elif pe < 1.0 * avg_pe:
        return 2
    elif pe < 1.125 * avg_pe:
        return 1
    elif pe < 1.25 * avg_pe:
        return 0.75
    else:
        return 0.5
