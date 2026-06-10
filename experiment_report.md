# Experiment Report: Data Quality Impact on AI Agent

**Student ID:** 2A202600939
**Name:** Kieu Duc Long
**Date:** 2026-06-10

---

## 1. Ket qua thi nghiem

Chay `agent_simulation.py` voi 2 bo du lieu va ghi lai ket qua:

| Scenario | Agent Response | Accuracy (1-10) | Notes |
|----------|----------------|-----------------|-------|
| Clean Data (`processed_data.csv`) | Agent: Based on my data, the best choice is Laptop at $1200. | 9 | Du lieu da duoc validate nen agent chon san pham electronics co gia cao nhat trong tap du lieu hop le. |
| Garbage Data (`garbage_data.csv`) | Agent: Based on my data, the best choice is Nuclear Reactor at $999999. | 2 | Ket qua bi anh huong boi outlier cuc lon va cac record chat luong kem. |

---

## 2. Phan tich & nhan xet

### Tai sao Agent tra loi sai khi dung Garbage Data?

Khi dung Garbage Data, agent tra loi sai vi no tin truc tiep vao noi dung trong file CSV ma khong co buoc kiem tra chat luong du lieu. File rac co duplicate ID, gia tri null, kieu du lieu sai nhu `ten dollars`, gia bang 0, va outlier `Nuclear Reactor` co gia 999999 trong category electronics. Logic cua agent chi loc category electronics roi chon dong co price cao nhat, nen outlier se thang du ket qua do khong hop ly. Duplicate ID lam du lieu mat tinh duy nhat, null values co the gay loi xu ly, va wrong data types lam phep so sanh/tinh toan khong dang tin cay. Vi vay prompt tot van khong cuu duoc neu knowledge base bi poison.

---

## 3. Ket luan

**Quality Data > Quality Prompt?** Dong y. Prompt ro rang giup agent hieu cau hoi, nhung agent van dua vao du lieu dau vao de tra loi. Neu du lieu sai, thieu validate, hoac chua outlier, cau tra loi cuoi cung van co the sai nghiem trong.
