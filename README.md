# Climate Guard

> Climate Risk & Carbon Credit Optimizer — ESG Intelligence Platform

[![Python 3.10+](https://img.shields.io/badge/python-3.10+-blue.svg)](https://www.python.org/downloads/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

**QuantumClimateGuard** is a plug-and-play Python toolkit for enterprise climate risk intelligence. It combines quantum-enhanced algorithms with classical analytics to model physical and transition risks, optimize carbon credit portfolios, generate TCFD-aligned reports, and plan net-zero pathways.
<img width="1903" height="968" alt="Screenshot 2026-05-30 184648" src="https://github.com/user-attachments/assets/dca8da4a-e818-4cac-8ad6-5f649911d15f" />


---

## Features

- **5 Quantum Pipelines**
  1. VQC Weather Pattern Embedding
  2. QAOA Carbon Credit Allocation
  3. VQE Asset Risk Valuation
  4. Quantum Kernel Geographic Clustering
  5. Density Matrix Climate Uncertainty
- **ESG & TCFD Reporting** — automated scoring, checklist evaluation, and gap analysis
- **Scope 1/2/3 Emissions Estimation** — per-asset and portfolio-level GHG accounting
- **Stranded Asset Risk** — transition-scenario probability modeling
- **Net-Zero Pathway Calculator** — compound reduction schedules with milestone tracking
- **AI Consensus Layer** — multi-provider LLM fallback with memory and skill extraction
- **8-Agent Swarm Consensus** — parallel specialist agents for deep synthesis
- **Rich CLI** — colorful terminal dashboards with tables and progress bars
- **CustomTkinter GUI** — dark-themed desktop interface (optional)

---

## Quick Start

### 1. Clone & Install

```bash
git clone https://github.com/quantumclimateguard/QuantumClimateGuard.git
cd QuantumClimateGuard
pip install -e .
```

### 2. Run It

```bash
# GUI mode (default)
quantum-climate-guard

# CLI demo (fast, classical)
quantum-climate-guard --cli --classical

# Programmatic demo
python -m quantum_climate_guard --demo --classical

# Force quantum mode (requires PyQPanda3)
quantum-climate-guard --cli
```

---

## Installation Options

```bash
# Core (classical mode)
pip install -e .

# With quantum backend (PyQPanda3 GPUQVM)
pip install -e ".[quantum]"

# With GUI
pip install -e ".[gui]"

# Everything
pip install -e ".[all]"

# Development
pip install -e ".[dev]"
```

---

## Environment Variables

Optional API keys for the AI consensus layer:

```bash
export NVIDIA_API_KEY="..."
export HF_API_KEY="..."
export XAI_API_KEY="..."
export OPENROUTER_API_KEY="..."
export ANTHROPIC_API_KEY="..."
export GEMINI_API_KEY="..."
export DEEPSEEK_API_KEY="..."

# Optional Telegram notifications
export TELEGRAM_BOT_TOKEN="..."
export TELEGRAM_CHAT_ID="..."
```

> **Never commit API keys.** The app reads them from environment variables only. Copy `.env.example` to `.env` and fill in your keys.

### Force Classical Mode

If you have PyQPanda3 installed but want to run fast classical demos:

```bash
# CLI flag
quantum-climate-guard --cli --classical

# Or environment variable
export QCG_CLASSICAL=1
python -m quantum_climate_guard --demo
```

---

## Usage Examples

### Python API

```python
from quantum_climate_guard import (
    ClimateEngine, generate_demo_data,
    net_zero_pathway, TCFD_checklist, scope_emissions_estimate
)

# Load sample data
assets, scenarios, credits = generate_demo_data()

# Run portfolio assessment
engine = ClimateEngine()
report = engine.assess_portfolio(assets, scenarios, credits)

print(f"ESG Score: {report.esg_score}/100")
print(f"Expected Annual Loss: ${report.expected_annual_loss:,.0f}")

# Net-zero pathway
emissions = scope_emissions_estimate(assets)
pathway = net_zero_pathway(emissions["portfolio_total_tCO2e"], target_year=2050)
print(f"Annual reduction rate: {pathway['compound_annual_reduction_rate']}%")

# TCFD checklist
tcfd = TCFD_checklist(
    governance={"board_climate_oversight": True, ...},
    strategy={"scenario_analysis_performed": True, ...},
)
print(f"TCFD Aligned: {tcfd['tcfd_aligned']} ({tcfd['overall_score_pct']}%)")
```

### CLI Demo
<img width="1914" height="981" alt="Screenshot 2026-05-30 184720" src="https://github.com/user-attachments/assets/7ed2a00b-3e1f-4db0-91c7-59247bacf513" />



```bash
python -m quantum_climate_guard --cli
```

Runs a full portfolio analysis with:
- ESG summary dashboard
- Per-asset risk tables
- Scenario comparison
- QAOA-optimized carbon credit selection
- Scope 1/2/3 emissions
- Net-zero pathway
- TCFD checklist
- Stranded asset analysis
- AI consensus review

---

## Project Structure

```
QuantumClimateGuard/
├── src/quantum_climate_guard/
│   ├── __init__.py          # Public API
│   ├── __main__.py          # CLI entry point
│   ├── models.py            # Dataclasses (Asset, Scenario, Credit, etc.)
│   ├── config.py            # Settings, constants, env vars
│   ├── quantum.py           # 5 quantum pipelines
│   ├── analytics.py         # Net-zero, TCFD, emissions, stranded assets
│   ├── engine.py            # ClimateEngine orchestrator
│   ├── demo.py              # Sample data generator
│   ├── cli.py               # Rich terminal interface
│   ├── gui.py               # CustomTkinter GUI
│   └── ai/
│       ├── gateway.py       # Multi-provider LLM fallback
│       ├── memory.py        # SQLite-backed skill memory
│       ├── consensus.py     # AI review + chatbox
│       └── swarm.py         # 8-agent swarm consensus
├── examples/
│   ├── cli_demo.py
│   └── api_example.py
├── tests/
│   ├── test_models.py
│   ├── test_analytics.py
│   └── test_engine.py
├── config/
│   └── default_config.json
├── pyproject.toml
├── requirements.txt
├── README.md
└── LICENSE
```

---

## Quantum Backend

Quantum pipelines auto-detect **PyQPanda3** and use GPUQVM when available. If PyQPanda3 is not installed, all pipelines gracefully fall back to high-performance classical approximations.

```bash
pip install pyqpanda3>=0.3.2
```

> Requires CUDA 12.8+ and compatible NVIDIA GPU for GPUQVM acceleration.

---

## Testing

```bash
pytest tests/
```

---

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Run tests and linting
5. Submit a pull request

---

## License

MIT License — see [LICENSE](LICENSE) for details.

---

## Disclaimer

QuantumClimateGuard is a research and analytical toolkit. Climate risk assessments, emissions estimates, and carbon credit valuations are illustrative and should be validated against professional auditors and regulatory standards before use in financial or compliance decisions.
