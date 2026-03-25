# CIS 5370 - Final Project`

## Set Up

### Tools and Dependencies

- Python v3.12
- [uv](https://docs.astral.sh/uv/)
  - An extremely fast Python package and project manager, written in Rust.

### Running the Project

```bash
uv add [list libraries]
```

```bash
uv sync
```

```bash
uv run main.py
```

## Project 1 - Intrusion Detection for Industrial Control Systems

**Goal**: Industrial Control Systems (ICS) operate critical infrastructure such as power grids, water treatment
facilities, and manufacturing plants. These systems rely on specialized communication protocols and deterministic control processes, which makes intrusion detection particularly challenging.

This project aims to design and evaluate an anomaly detection system for ICS environments using publicly available datasets and techniques inspired by recent research. You will compare different detection strategies and analyze how well they detect abnormal behavior while minimizing false alarms.

**Threat Model.** The attacker attempts to disrupt industrial operations by manipulating network
communications or process variables. Possible attacker capabilities include:

- Injecting malicious commands into ICS network traffic
- Modifying sensor or actuator messages
- Replaying or suppressing legitimate messages

The defender monitors network traffic or process logs and attempts to detect abnormal activity using
anomaly detection techniques.

**Design / Approach.** You will build a simplified intrusion detection pipeline consisting of the following stages: Data Collection and Processing, Feature Extraction, Detection Methods, and Evaluation.

**Technical Challenges.**

- Extracting meaningful features from ICS traffic or process data
- Designing detection models that generalize beyond a specific dataset
- Balancing detection accuracy with interpretability
- Handling noise or drift in system behavior

**Tools and Resources**

- Programming and analysis: Python (NumPy / Pandas, Scikit-learn, PyTorch or TensorFlow)
- Data visualization: Matplotlib or similar tools
- Datasets: publicly available ICS datasets such as SWaT or WADI

**Expected Results**

- an intrusion detection pipeline implemented in code
- experimental results comparing multiple detection methods
- analysis of detection accuracy and false positives
- a discussion of security implications and limitations

**Example Papers.**

- [GeCos Replacing Experts: Generalizable and Comprehensible Industrial Intrusion Detection USENIX Security 2025](https://www.usenix.org/system/files/usenixsecurity25-wolsing.pdf)
- [IPAL: Breaking up Silos of Protocol-dependent and Domain-specific Industrial Intrusion Detection Systems RAID 2022](https://arxiv.org/pdf/2111.03438.pdf)
- [ZOE: Content-Based Anomaly Detection for Industrial Control Systems DSN 2018](https://intellisec.de/pubs/2018-dsn.pdf)
- [DAICS: A Deep Learning Solution for Anomaly Detection in Industrial Control Systems](https://arxiv.org/pdf/2009.06299.pdf)
