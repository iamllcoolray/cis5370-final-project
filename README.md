# CIS 5370 - Final Project`

## Set Up

### Tools and Dependencies

- Python v3.12
- [uv](https://docs.astral.sh/uv/)
  - An extremely fast Python package and project manager, written in Rust.

### Running the Project

```bash
uv add numpy pandas scikit-learn matplotlib seaborn torch torchvision jupyter ipykernel tqdm scipy
```

```bash
uv sync
```

```bash
uv run main.py
```

## TODO

### Dataset

- [ ] Register and download the SWaT or WADI dataset (iTrust, Singapore)
- [ ] Explore and understand the dataset structure (sensor readings, labels, attack periods)
- [ ] Clean data (handle missing values, outliers)
- [ ] Normalize/scale features
- [ ] Split into train (normal behavior) and test (includes attacks) sets

### Feature Engineering

- [ ] Identify relevant sensors/actuators to use as features
- [ ] Compute rolling statistics (mean, variance, min/max over time windows)
- [ ] Compute rate-of-change features
- [ ] Explore correlations between sensors
- [ ] Document which features were selected and why

### Detection Models — Implement at least 2-3

- [ ] Baseline: threshold or rule-based detector
- [ ] Classical ML: Isolation Forest, One-Class SVM, or PCA-based
- [ ] Deep Learning: Autoencoder or LSTM-Autoencoder
- [ ] Train each model on normal data only
- [ ] Tune hyperparameters for each model

### Evaluation

- [ ] Run each model on labeled test data (with attack periods)
- [ ] Compute precision, recall, F1-score, and false positive rate for each model
- [ ] Plot ROC curves
- [ ] Plot confusion matrices
- [ ] Plot anomaly score distributions
- [ ] Compare all models in a summary results table

### Code Quality

- [ ] Organize code into logical modules/scripts
- [ ] Add comments and docstrings throughout
- [ ] Write a README with setup and run instructions
- [ ] Make sure experiments are fully reproducible (set random seeds, document dependencies)
- [ ] Create a `requirements.txt` or equivalent environment file
- [ ] Set up GitHub repo and commit regularly from the start
- [ ] Ensure repo is public and accessible from due date through 1 week after

### Technical Report (ACM Format, 6–10 pages, submit as PDF)

- [ ] Download ACM proceedings template (Word or LaTeX/Overleaf)
- [ ] Write Abstract
- [ ] Write Introduction / Motivation
- [ ] Write Related Work section (cite all 4 example papers at minimum)
- [ ] Write System Design & Methodology section
- [ ] Write Evaluation & Results section (include figures and tables)
- [ ] Write Discussion (security implications, limitations)
- [ ] Write Conclusion
- [ ] Add References
- [ ] Fill in Collaboration Table (required)
- [ ] Verify page count is within 6–10 pages (excluding references and appendix)
- [ ] Export final version as PDF

### Presentation (≤ 10 slides, ~10 minutes)

- [ ] Slide 1: Title + team members
- [ ] Slide 2: Problem motivation and threat model
- [ ] Slide 3: Dataset and data processing
- [ ] Slide 4: System design / pipeline overview
- [ ] Slide 5: Detection methods used
- [ ] Slide 6-7: Evaluation results (figures, tables)
- [ ] Slide 8: Security insights and limitations
- [ ] Slide 9: Demo (or link to demo video as backup)
- [ ] Slide 10: Conclusion / Q&A
- [ ] Every team member has a speaking role assigned
- [ ] Practice run timed — confirm it's under 12 minutes
- [ ] Prepare answers for likely Q&A questions

### Submission

- [ ] Submit GitHub repo link via Canvas "Text Entry" (do NOT upload code files)
- [ ] Submit report PDF to Canvas
- [ ] Confirm GitHub repo stays accessible for 1 week after due date

## Project 1 - Intrusion Detection for Industrial Control Systems

**Goal:** Industrial Control Systems (ICS) operate critical infrastructure such as power grids, water treatment
facilities, and manufacturing plants. These systems rely on specialized communication protocols and deterministic control processes, which makes intrusion detection particularly challenging.

This project aims to design and evaluate an **anomaly detection system for ICS environments** using publicly available datasets and techniques inspired by recent research. You will compare different detection strategies and analyze how well they detect abnormal behavior while minimizing false alarms.

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

## Project Report

Use ACM templates in either word doc or latex (overleaf) formats. Templates available at: [ACM Proceedings Templates](https://www.acm.org/publications/proceedings-template)

Instructions for each section is detailed in **slides**. Please note that a **collaboration table** is required for each report.

Please submit in **PDF format** with 6 – 10 pages (excluding references and appendix).

## Project Code

Use Github to manage your code - make sure the **code link** is available from **due** date until a **week later**.

Please submit the code link through **“text entry”** in Canvas. **DO NOT** submit the code to Canvas.

## Project Presentation

Each group will need to make no **more than 10 slides** to present the work. The presentation duration is around **10 minutes**. Presentations longer than 12 minutes will receive points reduction. The presentation will be live during class meetings. No need to submit slides to Canvas.

**Every** group member will need to participate in the presentation.

The presentation should highlight the **design decisions**, **evaluation results**, and **main security** insights obtained from the project. It should also include a **demo** of the implemented tool or system.

## Grading Rubric

| Category             | Points | Excellent (9-10)                                                                                                                  | Good (7-8)                                                                       | Fair (5-6)                                                                                | Poor (0-4)                                                              |
| -------------------- | ------ | --------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------- | ----------------------------------------------------------------------- |
| **Coding**           | 10     | Fully functional system with strong technical depth. Code is well-structured, documented, and experiments are reproducible.       | Major components implemented and mostly functional with minor issues.            | Partial implementation; several components incomplete or limited experimentation.         | Little or no working implementation; code unclear or missing.           |
| **Technical Report** | 10     | Clear motivation, methodology, and system design. Strong evaluation and analysis. Well written with proper references.            | Problem and approach described clearly; evaluation present but somewhat limited. | Basic explanation of the project with limited evaluation or weak analysis.                | Poorly written or missing sections; little or no meaningful evaluation. |
| **Presentation**     | 10     | Clear explanation of problem, approach, and results. Well-designed slides and confident delivery. Questions answered effectively. | Understandable presentation with minor clarity issues; slides mostly clear.      | Key ideas not clearly explained; slides poorly organized; limited responses to questions. | Presentation lacks structure; difficult to understand the project.      |

**Note:** Each team member receives the same base score by default. If the collaboration table shows significant imbalance in task contributions, individual scores may be adjusted accordingly.
