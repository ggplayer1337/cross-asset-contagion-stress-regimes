# Cross-Asset Contagion in Stress Regimes

### Evidence from Bitcoin Crash Events and Equity Correlation Breakdown (2020–2025)

[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://www.python.org/)
[![TensorFlow](https://img.shields.io/badge/TensorFlow-2.0+-orange.svg)](https://www.tensorflow.org/)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

---

## 🎯 Abstract

Traditional portfolio theory assumes that defensive, low-beta equities provide diversification benefits during periods of market stress. This study examines whether those benefits persist during crypto-led liquidity shocks.

Using 2,199 trading days between 2020 and 2025, I analyze regime-dependent correlations between Bitcoin and selected equity groups. Stress regimes are defined as weekly Bitcoin drawdowns exceeding 10%, consistent with institutional market conventions for correction-level declines.

**Key Finding:** The diversification gap between high-beta and defensive equities collapses by **89.5%** during Bitcoin crash periods (from 0.293 to 0.031), indicating a structural breakdown in traditional portfolio diversification when it is most needed.

---

## 📊 Key Results

### Correlation During Regimes

| Regime | High-Beta Equities | Defensive Equities | Diversification Gap |
|--------|-------------------|-------------------|---------------------|
| **Normal** | 0.364 | 0.071 | **0.293** |
| **Crisis** | 0.446 | 0.415 | **0.031** |
| **Change** | +0.081 (+22.3%) | +0.344 (+485.1%) | **-0.263 (89.5% reduction)** |

### Interpretation

During Bitcoin crash regimes:
- Defensive equities (J&J, Coca-Cola, P&G) correlation with Bitcoin increased **485%**
- High-beta equities (Coinbase, Tesla, NVIDIA) correlation increased **22.3%**
- The protective gap between "safe" and "risky" assets nearly disappeared
- **Result:** Traditional diversification assumptions temporarily fail

---

## 💡 Research Question

**Do Bitcoin crash events coincide with a regime-dependent breakdown in the correlation structure between high-beta and defensive equities?**

**Answer:** Yes. The 89.5% gap compression indicates Bitcoin crashes signal systemic liquidity stress affecting all equity classes.

---

## 🏗️ Methodology

### Data
- **Period:** January 2020 – January 2025 (2,199 trading days)
- **Source:** Yahoo Finance (daily adjusted closing prices)
- **Assets:** Bitcoin + 8 equities across two behavioral groups

### Asset Selection

**Group A: High-Beta / Sentiment-Driven Equities**
- Coinbase (COIN)
- MicroStrategy (MSTR)
- Tesla (TSLA)
- NVIDIA (NVDA)

*Rationale:* High volatility, growth-oriented, sensitive to retail sentiment and liquidity conditions

**Group B: Defensive / Low-Beta Equities**
- Johnson & Johnson (JNJ)
- Coca-Cola (KO)
- Procter & Gamble (PG)

*Rationale:* Cash-flow stable, dividend-paying, commonly used for capital preservation

### Regime Definition

**Crisis Regime:** Weekly Bitcoin return ≤ -10%

This threshold aligns with institutional market conventions:

| Market Term | Definition |
|-------------|------------|
| Pullback | ~5% decline |
| **Correction** | **~10% decline** ← Our threshold |
| Bear Market | ~20% decline |

**Results:** 146 crisis days (6.6%), 2,052 normal days (93.4%)

### Analysis Steps

1. Compute daily percentage returns
2. Identify stress regimes using rolling 7-day Bitcoin returns
3. Segment data into Normal and Crisis regimes
4. Calculate Pearson correlations for each regime
5. Compare correlation structures and measure gap compression

---

## 📈 Visualizations

### 1. Correlation Convergence During Crises

*[Chart showing defensive equities reaching ~0.4 correlation, matching high-beta stocks]*

### 2. Individual Asset Exposure Ranking

*[Horizontal bar chart showing correlation changes for each stock]*

### 3. Regime-Dependent Dynamics

*[Side-by-side comparison of Normal vs Crisis correlations]*

### 4. LSTM Model Training

*[Training/validation loss curves for predictive model]*

---

## 🔬 Key Findings

### 1. Systemic Contagion Detected

During Bitcoin crash periods, defensive equities become **moderately correlated** with Bitcoin (0.415), nearly matching high-beta equities (0.446). This convergence indicates:

- Bitcoin functions as a **high-frequency proxy for systemic liquidity stress**
- Traditional "flight-to-quality" assumptions break down
- Diversification benefits weaken precisely when most needed

### 2. Practical Implications

**For Portfolio Managers:**
- Static correlation assumptions underestimate risk during crypto-led stress
- Traditional 60/40 allocations may face larger drawdowns than expected
- Risk models (VaR, Expected Shortfall) may underestimate tail risk

**For Risk Management:**
- Bitcoin volatility serves as early warning indicator
- Stress testing should incorporate crypto-led liquidity scenarios
- Dynamic correlation models needed for accurate risk assessment

---

## 🛠️ Technical Stack

- **Python 3.8+**
- **Data:** yfinance
- **Analysis:** pandas, numpy, scipy
- **Visualization:** matplotlib, seaborn
- **Machine Learning:** TensorFlow/Keras (LSTM)
- **Statistical Methods:** Pearson correlation, regime detection

---

## 🚀 Usage

### Installation

```bash
pip install yfinance pandas numpy matplotlib seaborn scikit-learn tensorflow
```

### Running the Analysis

1. Clone this repository:
```bash
git clone https://github.com/[your-username]/cross-asset-contagion-stress-regimes.git
cd cross-asset-contagion-stress-regimes
```

2. Open the Jupyter notebook:
```bash
jupyter notebook Cross_Asset_Contagion_in_Stress_Regimes.ipynb
```

3. Run all cells to reproduce the analysis

**Expected Runtime:** ~10 minutes (including LSTM training)

---

## 📂 Project Structure

```
cross-asset-contagion-stress-regimes/
├── Cross_Asset_Contagion_in_Stress_Regimes.ipynb    # Main analysis
├── Cross-Asset_Contagion_in_Stress_Regimes.pdf      # Full documentation
├── README.md                                         # This file
├── requirements.txt                                  # Python dependencies
├── LICENSE                                           # MIT License
└── images/                                           # Visualizations
    ├── crisis_correlation_levels.png
    ├── individual_stock_ranking.png
    ├── regime_comparison.png
    ├── key_findings_summary.png
    └── lstm_training_loss.png
```

---

## ⚠️ Limitations & Future Work

### Current Limitations

1. **Regime Definition:** Threshold-based approach; alternative definitions (VIX-based, HMM) could yield different results
2. **Asset Selection:** Small, representative sample prioritizes interpretability; broader indices may show different patterns
3. **Statistical Rigor:** No formal significance testing (confidence intervals); acknowledged as future enhancement
4. **Causality:** Analysis identifies correlation patterns, not causal mechanisms; cannot distinguish Bitcoin-specific from general market effects
5. **Data Quality:** Survivorship bias (selected firms survived 2020-2025); potential microstructure issues with daily data

### Future Enhancements

#### High Priority
- Bootstrap confidence intervals for statistical significance
- Threshold sensitivity analysis (-5%, -8%, -12%, -15%)
- VIX control to isolate Bitcoin-specific effects

#### Medium Priority
- Rolling correlation analysis (time-varying dynamics)
- DCC-GARCH models for dynamic correlations
- International market extension (Europe, Asia)

#### Advanced
- Network analysis of systemic importance
- Causal inference (Granger causality, structural VAR)
- Portfolio backtesting with dynamic allocation

See full documentation PDF for detailed research roadmap.

---

## 📚 References

This project builds on established research in financial contagion:

1. **Forbes, K., & Rigobon, R. (2002).** *No contagion, only interdependence: measuring stock market comovements.* Journal of Finance, 57(5), 2223-2261.

2. **Corbet, S., Meegan, A., Larkin, C., Lucey, B., & Yarovaya, L. (2018).** *Exploring the dynamic relationships between cryptocurrencies and other financial assets.* Economics Letters, 165, 28-34.

3. **Baur, D. G., & Dimpfl, T. (2021).** *The volatility of Bitcoin and its role as a medium of exchange and a store of value.* Empirical Economics, 61, 2663-2683.

4. **Kaminsky, G. L., & Reinhart, C. M. (2000).** *On crises, contagion, and confusion.* Journal of International Economics, 51(1), 145-168.

---

## 👤 Author

**Manasi Nandrajog**
- MSc Big Data Science (Distinction), Queen Mary University of London
- BSc Information Technology (9.6/10 CGPA)
- Data & Admin Coordinator, School of Business and Management, QMUL
- [LinkedIn](https://linkedin.com/in/[your-profile]) | [Email](mailto:manasi.nandrajog@example.com)

---

## 🤝 Contributing

This is an academic research project. Suggestions and feedback are welcome! Please open an issue or submit a pull request.

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## 🙏 Acknowledgments

- Data provided by Yahoo Finance via `yfinance` library
- Inspired by literature on cross-asset contagion and systemic risk
- Developed as part of career transition portfolio (December 2024 - January 2025)

---

## 📧 Contact

For questions about this research or collaboration opportunities:
- Email: [your-email]
- LinkedIn: [your-linkedin]
- Portfolio: [your-website]

---

**⭐ If you found this research interesting, please consider starring the repository!**

---

### Citation

If you use this work in your research, please cite:

```bibtex
@misc{nandrajog2025crossasset,
  author = {Nandrajog, Manasi},
  title = {Cross-Asset Contagion in Stress Regimes: Evidence from Bitcoin Crash Events},
  year = {2025},
  publisher = {GitHub},
  url = {https://github.com/[your-username]/cross-asset-contagion-stress-regimes}
}
```
