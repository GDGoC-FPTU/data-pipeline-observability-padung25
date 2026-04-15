[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-2e0aaae1b6195c2367325f4f02e2d04e9abb55f0b24a779b69b11b9e10269abc.svg)](https://classroom.github.com/online_ide?assignment_repo_id=23574017&assignment_repo_type=AssignmentRepo)
# Day 10 Lab: Data Pipeline & Data Observability

**Student Email:** panhdung2511@gmail.com   
**Name:** Phạm Anh Dũng

---

## Mo ta

Thực hiện các yêu cầu trong solution.py
Chạy các file .py còn lại để có kết quả điền vào experiment_report.md

---

## Cach chay (How to Run)

### Prerequisites
```bash
pip install pandas
```

### Chay ETL Pipeline
```bash
python solution.py
```

### Chay Agent Simulation (Stress Test)
```bash
 python agent_simulation.py 
 Testing with CLEAN data: Agent: Based on my data, the best choice is Laptop at $1200. Testing with GARBAGE data: Agent: Based on my data, the best choice is Nuclear Reactor at $999999.
```

---

## Cau truc thu muc

```
├── solution.py              # ETL Pipeline script
├── processed_data.csv       # Output cua pipeline
├── experiment_report.md     # Bao cao thi nghiem
└── README.md                # File nay
```

---

## Ket qua

Tóm tắt kết quả: 3 records được giữ lại, 2 cái bị loại
