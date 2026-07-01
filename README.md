# AI Powered Security Alert Analyzer
A Python-based security monitoring tool that analyzes authentication logs, detects suspicious activity, and generates concise AI-powered insights.


## 🚀 Features
* Parses login logs (failed, invalid, successful attempts)
* Assigns severity levels: LOW, MEDIUM, HIGH, CRITICAL
* Clean structured output (timestamp → IP → attempts → level → analysis)
* Color-coded and bold severity indicators (Tkinter UI)
* Short AI-generated analysis (max 3 lines for fast decision-making)


## 🧠 Why this project?
Security analysts don’t have time to read long logs.

This tool transforms raw log data into:

* Structured alerts
* Clear severity levels
* Quick AI-based explanations

Inspired by SIEM tools, but enhanced with AI for faster understanding.


## 🛠 Tech Stack
* Python
* Tkinter (UI)
* Requests (API calls)
* Ollama (Local LLM)

## ⚙️ How it works
1. Reads log file (`log.txt`)
2. Extracts login activity per IP
3. Calculates severity level
4. Displays structured alerts in UI
5. Generates short AI analysis for high-risk alerts


## 📸 Example Output

<img width="811" height="492" alt="Screenshot 2026-04-24 153054" src="https://github.com/user-attachments/assets/f5ac6dbc-52cd-43fc-afc9-444b24121ab3" />



## ▶️ Setup & Run

Install dependencies:
```
pip install requests
```
Make sure Ollama is running locally.

Run the project:
```
python main.py
```

## 📌 Project Highlights
* Built a mini SIEM-style alert analyzer
* Integrated local AI for security insights
* Focused on clarity and real-world usability

## 🛡️ Security, Governance & Compliance Framework (NIST CSF 2.0 / EU AI Act)

This tool was architected from the ground up to prioritize **Data Sovereignty** and **Secure AI Governance**, addressing the critical compliance gaps found in traditional cloud-dependent AI integrations.

### 1. Data Privacy & Sovereignty (NIST CSF 2.0: PR.DS / UK GDPR)
* **The Compliance Challenge:** Forwarding enterprise system logs containing sensitive IP addresses and user metrics to third-party cloud LLM providers (e.g., OpenAI, Anthropic) violates standard Data Processing Agreements (DPAs) and strict data privacy regulations like UK GDPR.
* **Architecture Mitigation:** By utilizing **Ollama** to host models locally, this tool enforces a **zero-data-leakage architecture**. 100% of log ingestion, calculation, and AI generation occurs locally on the host machine. No telemetry or corporate log data is transmitted over the internet.

### 2. Mitigation of AI Hallucinations & Risk Management (NIST CSF 2.0: DE.AE)
* **The Compliance Challenge:** Large Language Models are prone to nondeterministic outputs and hallucinations, which can result in the misclassification of a critical security threat as a low-level event.
* **Architecture Mitigation:** The tool implements a **Deterministic/Probabilistic Hybrid Control Strategy**. The Python core logic explicitly calculates the numerical threat severity *before* involving the LLM. The AI engine is strictly confined to generating the 3-line contextual summary, ensuring that model drift or hallucination can never downgrade a critical system alert.

### 3. Supply Chain Integrity & Asset Management (NIST CSF 2.0: ID.AM)
* **The Compliance Challenge:** Reliance on open-source Python packages (`requests`, `tkinter`) and local model weights introduces software supply chain vulnerabilities.
* **Architecture Mitigation:** The tool enforces strict dependency tracking. All required software components are locked via a standardized `requirements.txt` file to allow continuous vulnerability scanning and software inventory audits.

### 4. Alignment with Emerging Global AI Regulations
* **EU AI Act / UK AI Regulation Compliance:** Under modern frameworks, automated cybersecurity infrastructure must avoid systemic bias and maintain a clear audit trail. This tool satisfies these constraints by providing structured, time-stamped outputs (`timestamp → IP → attempts → level → analysis`) ensuring full traceability and accountability for compliance auditors.

## 🔗 Future Improvements
* Real-time log monitoring
* Support for system logs (auth.log)
* Alert filtering and dashboard features

https://github.com/zibdrs83/AI-Powered-Security-Alert-Analyzer.git
