# AI-Assisted Power Estimation of Digital Circuits

Power estimation is a critical step in digital circuit design. Conventional EDA-based power reports are accurate but **computationally expensive, time-consuming, and resource-heavy**.  
This project introduces an **AI-assisted estimator** that learns from RTL/synthesis features to predict power consumption quickly, without running full-fledged EDA power analysis.  

- **Features:**  
  - Bridges **VLSI CAD** and **AI/ML**.  
  - Provides **near-instant feedback** to designers, enabling faster design iterations.  
  - Uses **open datasets, synthesis tools, and ML frameworks**, making it accessible and reproducible.  
  - Opens scope for **research benchmarking** and **EDA acceleration**.


## Objectives

1. Collect RTL/synthesis features and EDA-generated power reports for a set of benchmark circuits.  
2. Train AI/ML models (SVM, Random Forest, DNN) to map design features → power consumption.  
3. Compare prediction accuracy vs. standard EDA reports.  
4. Provide a lightweight **tool/script** for designers to estimate power quickly during design iterations.  

---

## Methodology
```text
Circuit RTL → Synthesis → Feature Extraction ───────────────┐
                                                            │
                                                    Training Dataset
                                                            │
                                         ┌───────── ML Models ─────────┐
                                         │                             │
                                    Power Estimator             Evaluation & Tuning
                                         │
                                         ▼
                               Fast Power Predictions
+--------------------+       +---------------------+
|   RTL Circuits     | ----> |   Logic Synthesis   |
+--------------------+       +---------------------+
                                    |
                                    v
                         +----------------------+
                         | Feature Extraction   |
                         +----------------------+
                                    |
                                    v
              +---------------------------------------------+
              | ML Models (SVM / RF / DNN)                  |
              | - Train on dataset                          |
              | - Validate accuracy                         |
              +---------------------------------------------+
                                    |
                                    v
                      +-----------------------------+
                      | Power Prediction Tool       |
                      | (fast estimation vs. EDA)   |
                      +-----------------------------+

```


## Tools Used

- **EDA & Synthesis:** Yosys, OpenROAD, Synopsys.  
- **Datasets:** OpenCores, VTR benchmarks, or generated RTL modules.  
- **Machine Learning:** Python (scikit-learn, TensorFlow/PyTorch).  
- **Environment:** Linux, Jupyter notebooks, GitHub repo for collaboration.  

---

## Expected Outcomes

- An **AI-assisted tool** that predicts digital circuit power consumption.  
- Benchmark results comparing ML predictions vs. EDA reports.  
- Open-source dataset and trained models for reproducibility.  
- Scope for future integration into design flows or FPGA prototyping.  

---

## Contributors

- *Karthika G S*  

---

## References

1. OpenCores benchmark circuits  
2. [Yosys Open Synthesis Suite](https://yosyshq.net/yosys/)  
3. [OpenROAD Project](https://theopenroadproject.org/)  
4. Research papers on ML-based EDA acceleration  

---


