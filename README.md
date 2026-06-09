# UPI Transaction Performance & Reliability Analysis

I built this project to understand how reliable UPI payment systems actually are under real-world conditions. With 250K+ transactions in the dataset, I wanted to go beyond surface-level analysis and answer some specific questions that I felt were worth investigating.

---

## Why I Built This

UPI processes billions of transactions every day in India. A 5% failure rate sounds small, but at scale that means millions of failed payments. I wanted to dig into whether failures are random or concentrated around specific patterns like peak hours, device types, or channels.

---

## What I Was Trying to Find Out

- What is the actual failure rate across the dataset?
- Do failures spike during peak hours or is the system stable under load?
- Are certain devices or channels more prone to failures?
- Has performance been consistent over time or are there degrading trends?

---

## Tech Stack

- **Python (Pandas, NumPy)** for data cleaning, feature engineering and KPI computation
- **Jupyter Notebook** for analysis and documentation
- **Tableau** for building the dashboard

---

## What the Data Looked Like

The dataset had 250,000+ UPI transaction records with fields like transaction timestamp, status, device type, channel and amount. Before any analysis I had to clean it properly, handle nulls, parse timestamps, extract hour and month features, and flag outliers.

---

## How I Approached It

I started with basic data cleaning and then moved into feature engineering. I created hour buckets, a peak/off-peak flag based on transaction volume, and monthly period markers. From there I computed KPIs using Pandas aggregations and built the Tableau dashboard to visualise the patterns.

The KPIs I focused on:

- **Failure Rate** per time window and channel
- **Hourly Load** to map transaction volume across the day
- **Throughput Ratio** to measure how much of the load was successfully processed
- **Channel Risk** normalised failure rate by channel volume

---

## What I Found

The overall failure rate sits at around 5% and stays pretty consistent throughout the dataset. What surprised me was that peak hours do not actually drive higher failures. I expected to see a correlation there but the data did not support it, which suggests the system handles load well.

The more interesting finding was around channels. The web channel had a slightly higher failure rate compared to mobile. That is worth investigating further because it could point to infrastructure or session handling differences.

Month-on-month the system looked stable with no major spikes or downward trends.

---
## How to Run

**Step 1 — Clone the repository**
```bash
git clone https://github.com/Shrishti1211/upi-transaction-analysis.git
```

**Step 2 — Navigate into the project folder**
```bash
cd upi-transaction-analysis
```

**Step 3 — Install the required libraries**
```bash
pip install pandas numpy jupyter
```

**Step 4 — Launch the notebook**
```bash
jupyter notebook notebooks/upi_analysis.ipynb
```


## Project Structure

Here is how the repository is organised:
