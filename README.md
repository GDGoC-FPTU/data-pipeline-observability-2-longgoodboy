# Day 10 Lab: Data Pipeline & Data Observability

**Student ID:** 2A202600939
**Student Email:** mailcualongk@gmail.com
**Name:** Kieu Duc Long

---

## Mo ta

Bai lab nay xay dung mot ETL pipeline don gian bang Python va pandas. Pipeline doc du lieu tu `raw_data.json`, loai bo record khong hop le, chuan hoa du lieu, tinh gia sau giam gia 10%, them timestamp xu ly, va luu ket qua ra `processed_data.csv`. Bai lab cung co phan stress test de so sanh cach mot agent tra loi khi dung du lieu sach va du lieu rac.

---

## Cach chay (How to Run)

### Prerequisites

```bash
pip install pandas pytest
```

### Chay ETL Pipeline

```bash
python solution.py
```

Ket qua se tao file `processed_data.csv` trong thu muc goc cua repo.

### Chay Agent Simulation (Stress Test)

```bash
python generate_garbage.py
python agent_simulation.py
```

Neu muon test dung file clean trong repo nay, co the goi truc tiep ham `simulate_agent_response` voi `processed_data.csv` va `garbage_data.csv`.

### Chay autograder local

```bash
python -m pytest tests/test_autograder.py -q
```

---

## Cau truc thu muc

```text
solution.py              # ETL Pipeline script
raw_data.json            # Du lieu dau vao
processed_data.csv       # Output cua pipeline
experiment_report.md     # Bao cao thi nghiem Clean vs Garbage data
generate_garbage.py      # Tao garbage_data.csv
agent_simulation.py      # Mo phong agent doc du lieu
tests/test_autograder.py # Test cham diem tu dong
```

---

## Ket qua

Pipeline doc 5 records tu `raw_data.json`. Sau validation, 3 records hop le duoc giu lai va 2 records bi loai vi `price <= 0` hoac `category` rong. Output `processed_data.csv` co them cot `discounted_price` bang `price * 0.9` va cot `processed_at` de quan sat thoi diem xu ly. Stress test cho thay clean data giup agent chon Laptop hop ly, trong khi garbage data lam agent chon outlier Nuclear Reactor.
