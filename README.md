# MTFPy-Framework-Axiom-Automation-Qualcomm
Modem Test framework with execution platform in Axiom 

mtfpy-framework/
│
├── config/                # Configuration files (devices, network, env)
│   ├── device_config.yaml
│   ├── network_config.yaml
│
├── test_cases/            # All test scripts
│   ├── test_call.py
│   ├── test_data.py
│   ├── test_sms.py
│
├── libraries/             # Reusable functions / utilities
│   ├── modem_lib.py
│   ├── network_lib.py
│   ├── adb_lib.py
│
├── drivers/               # Device interfaces (ADB, QXDM, AT commands)
│   ├── adb_driver.py
│   ├── at_driver.py
│
├── keywords/              # High-level reusable keywords (like Robot Framework)
│   ├── call_keywords.py
│   ├── data_keywords.py
│
├── logs/                  # Execution logs
│   ├── run.log
│
├── reports/               # Test reports
│   ├── report.html
│   ├── result.xml
│
├── utils/                 # Helper utilities
│   ├── logger.py
│   ├── parser.py
│
├── test_data/             # Input data for test cases
│   ├── test_data.json
│
├── main.py                # Test runner / entry point
├── requirements.txt       # Dependencies
└── README.md




->Key Components

1.Config Layer
Stores device info, SIM configs, APN, bands
Helps run same test across multiple device

2.Test Cases Layer
Actual test scenarios like:
Call setup / teardown
Data attach / detach
Handover / mobility
Written using reusable functions

3. Libraries Layer
Core logic implementation:
Send AT commands
Trigger calls
Validate logs

4. Drivers Layer
Interface to hardware/tools:
ADB (Android Debug Bridge)
QXDM / Qualcomm tools
Serial communication

5. Keywords Layer
High-level abstraction:
make_call()
check_network_attach()
Improves reusability + readability

6. Logging & Reporting
Logs → Debugging failures
Reports → Pass/Fail summary (HTML/XML)

->Integrates with Jenkins for CI/CD
->Can capture logs from:QXDM

->Axiom is Qualcomm’s internal automation platform
->Used for modem validation, protocol testing, and end-to-end telecom scenarios (LTE/5G)
Provides:
Test orchestration
Device control
Logging (QXDM, diag logs)
Result analysis


MTFPy = Test framework (Python-based automation layer)
Axiom = Execution platform / ecosystem


->Integration Architecture

MTFPy Test Cases
        ↓
Keywords / Libraries (Python)
        ↓
Axiom APIs / Interfaces
        ↓
Device Control + Network Simulation
        ↓
Logs Collection (QXDM, Diag)
        ↓
Axiom Reporting Dashboard


MTFPy = Selenium test scripts
Axiom = Test execution platform like Jenkins + Grid + Reporting combined

->MTFPy handles:
Test logic
Automation scripts
Validation
Axiom handles:
->Test execution orchestration
Device allocation
Network simulation
Log collection & reporting


“MTFPy provides the Python-based automation layer for writing modem test cases, while Qualcomm Axiom acts as the execution and orchestration platform that manages devices, logs, and reporting.”
