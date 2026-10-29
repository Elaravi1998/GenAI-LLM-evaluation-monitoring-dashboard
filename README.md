# 📊 LLM Evaluation & Monitoring Dashboard

A Python-based Generative AI project for evaluating and monitoring LLM application performance across answer-quality proxies, latency, estimated cost, success rate, and user feedback.

This project provides a notebook-based workflow for analyzing LLM traces, comparing models, identifying potential quality issues, and exporting metrics for dashboards and reporting.

> **Note:** The included data is synthetic. The project currently performs batch analysis rather than real-time monitoring. Token-overlap scores are illustrative heuristics, not definitive measures of correctness.

## 🚀 Features

- 📈 LLM application performance analysis
- 🧠 Reference-based answer-quality evaluation
- ⚡ Average and P95 latency analysis
- 💰 Estimated API cost tracking
- ✅ Request success and error-rate monitoring
- 🔍 Model-level performance comparisons
- 📊 Matplotlib charts and visualizations
- 🚨 Error and low-quality review queue
- 📁 CSV and JSON metric exports
- 📓 Interactive Python Jupyter Notebook

## 🛠️ Technology Stack

| Technology | Purpose |
|---|---|
| Python | Main programming language |
| Jupyter Notebook | Interactive analysis |
| pandas | Data processing and analysis |
| NumPy | Numerical operations |
| Matplotlib | Data visualization |

## 🏗️ Project Architecture

```text
             LLM Application Traces
                       |
                       v
              Data Preparation
                       |
                       v
               Metric Calculation
                       |
           +-----------+-----------+
           |           |           |
           v           v           v
        Quality     Latency       Cost
        Metrics     Metrics     Metrics
           |           |           |
           +-----------+-----------+
                       |
                       v
               Model Comparison
                       |
                       v
               Visual Analytics
                       |
                       v
               CSV / JSON Exports
```

## 📁 Repository Structure

```text
llm-evaluation-monitoring-dashboard/
│
├── llm_evaluation_monitoring_dashboard.ipynb
├── requirements.txt
├── .gitignore
└── README.md
```

## ⚙️ Installation

### 1. Clone the repository

```bash
git clone https://github.com/YOUR_USERNAME/llm-evaluation-monitoring-dashboard.git
cd llm-evaluation-monitoring-dashboard
```

Replace `YOUR_USERNAME` with your GitHub username.

### 2. Create a virtual environment

**Windows PowerShell**

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
```

**macOS/Linux**

```bash
python3 -m venv .venv
source .venv/bin/activate
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Launch Jupyter Notebook

```bash
jupyter notebook llm_evaluation_monitoring_dashboard.ipynb
```

Run the notebook cells from top to bottom.

The notebook generates evaluation metrics, comparison tables, charts, and export files.

## 📊 Evaluation Metrics

| Metric | Description |
|---|---|
| Total Requests | Total number of requests in the dataset |
| Success Rate | Percentage of requests marked successful |
| Error Rate | Percentage of requests marked as errors |
| Average Latency | Mean response time in milliseconds |
| P95 Latency | 95th-percentile response time |
| Estimated Cost | Sum of illustrative per-request costs |
| Token-F1 Proxy | Token overlap between a generated answer and its reference |
| User Feedback | Average rating in the sample dataset |
| Low-Quality Proxy Rate | Percentage of records below a configurable token-overlap threshold |

### Why monitor these metrics?

- **Quality:** Identify responses that may need closer review.
- **Latency:** Understand response-time performance.
- **Cost:** Compare estimated model expenses.
- **Reliability:** Track failed requests.
- **Feedback:** Identify examples that users rated poorly.

No single metric is sufficient to evaluate an LLM application. Combine automated metrics with task-specific evaluation and human review.

## 📈 Visualizations

The notebook generates charts for:

1. Average latency by model
2. Total estimated cost by model
3. Average token-F1 proxy by model
4. Success rate by model
5. Average latency trends over time

These visualizations help compare models and identify potential performance issues.

## 📂 Generated Output Files

After running the notebook, an `llm_monitoring_outputs/` folder will contain:

```text
llm_monitoring_outputs/
├── evaluation_records.csv
├── model_summary.csv
├── dashboard_kpis.csv
├── dashboard_kpis.json
└── review_queue.csv
```

| File | Purpose |
|---|---|
| `evaluation_records.csv` | Individual records and computed metrics |
| `model_summary.csv` | Model-level metric comparisons |
| `dashboard_kpis.csv` | Headline performance metrics |
| `dashboard_kpis.json` | Headline metrics in JSON format |
| `review_queue.csv` | Errors and potentially low-quality examples |

These exports can be used in spreadsheet software, a BI tool, or a future interactive dashboard.

## 🔌 Using Real LLM Data

To adapt the project for a real application, replace the synthetic dataset with appropriately redacted traces from your LLM application.

Recommended fields include:

- Request ID and timestamp
- Model name and task type
- Reference answer or evaluator result
- Generated answer, subject to your privacy policy
- Latency and token counts
- Actual or estimated cost
- Request status
- User feedback

Prefer provider-reported token usage and cost information when available. If cost is calculated from token counts, use a versioned pricing configuration and clearly label the result as an estimate.

## ⚠️ Limitations

- The included dataset contains synthetic examples.
- Cost values are illustrative rather than live provider prices.
- Token overlap does not reliably measure semantic similarity, factual correctness, relevance, or safety.
- The notebook does not call an LLM API.
- The current implementation analyzes data in batches; it does not provide live monitoring or automatic alerting.

## 🔐 Production Considerations

Before using real application data:

- Redact secrets and sensitive personal information.
- Restrict access to prompts, responses, and logs.
- Define data-retention policies.
- Add error handling and data validation.
- Monitor latency, errors, and cost spikes.
- Combine automated evaluation with human review.
- Use task-appropriate quality metrics.

## 🛣️ Future Enhancements

- [ ] Add human-labelled evaluation datasets.
- [ ] Add semantic evaluation and a calibrated LLM-as-judge workflow.
- [ ] Integrate real LLM application traces.
- [ ] Add prompt-version tracking.
- [ ] Track retrieval quality and tool-call success.
- [ ] Add safety and hallucination evaluation metrics.
- [ ] Add automated alerts for latency, errors, and cost spikes.
- [ ] Build an interactive Streamlit dashboard.
- [ ] Integrate with an observability platform.
- [ ] Add access controls and data-retention policies.

## 🎯 Learning Outcomes

This project demonstrates practical experience with:

- LLM evaluation workflows
- Performance and latency analysis
- Cost monitoring
- Data-driven model comparisons
- Evaluation metric design
- Error analysis and quality review
- Data visualization
- Exporting metrics for reporting

## 📜 License

Choose a license before publishing, such as the MIT License, and include the corresponding `LICENSE` file.

---

**Built with Python, Jupyter Notebook, and Generative AI evaluation techniques.**
