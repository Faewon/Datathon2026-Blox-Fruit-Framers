# 🏆 VinTelligent Datathon 2026 — Blox Fruit Farmers

Đây là repository tổng hợp toàn bộ lời giải của nhóm **Blox Fruit Farmers** cho cuộc thi **VinTelligent Datathon 2026**, bao gồm 3 phần độc lập.

---

## Tổng quan các phần

| Phần | Notebook | Nội dung | README chi tiết |
|------|----------|----------|-----------------|
| **Phần 1** | `vintelligent_datathon_2026_MCQ.ipynb` | 10 câu hỏi trắc nghiệm — tính toán trực tiếp từ dữ liệu | [README_Part1_MCQ.md](README_Part1_MCQ.md) |
| **Phần 2** | `vintelligent-datathon-2026-Part_2.ipynb` | Phân tích kinh doanh (EDA & Business Insights) | [README_Part2_EDA.md](README_Part2_EDA.md) |
| **Phần 3** | `vintelligent-datathon-2026-Part_3.ipynb` | Dự báo doanh thu (Sales Forecasting — GBR V3) | [README_Part3_Forecasting.md](README_Part3_Forecasting.md) |

---

## Cấu trúc thư mục đề xuất

```text
vintelligent-datathon-2026/
├── data/                              # Thư mục chứa toàn bộ dữ liệu
│   ├── orders.csv
│   ├── order_items.csv
│   ├── products.csv
│   ├── promotions.csv
│   ├── payments.csv
│   ├── returns.csv
│   ├── customers.csv
│   ├── geography.csv
│   ├── inventory.csv
│   ├── web_traffic.csv
│   ├── sales.csv
│   └── sample_submission.csv
│
├── vintelligent_datathon_2026_MCQ.ipynb        # Phần 1: MCQ
├── vintelligent-datathon-2026-Part_2.ipynb     # Phần 2: EDA
├── vintelligent-datathon-2026-Part_3.ipynb     # Phần 3: Forecasting
│
├── README.md                          # File này
├── README_Part1_MCQ.md
├── README_Part2_EDA.md
└── README_Part3_Forecasting.md
```

---

## Dữ liệu

Toàn bộ dữ liệu cuộc thi được cung cấp tại Kaggle dataset `datathon-2026-round-1`:

| File | Mô tả |
|------|-------|
| `orders.csv` | Thông tin đơn hàng, trạng thái, phương thức thanh toán |
| `order_items.csv` | Chi tiết sản phẩm trong từng đơn hàng |
| `products.csv` | Danh mục sản phẩm, giá, COGS, phân khúc |
| `promotions.csv` | Thông tin chương trình khuyến mãi |
| `payments.csv` | Chi tiết thanh toán, kỳ trả góp |
| `returns.csv` | Lịch sử trả hàng và lý do |
| `customers.csv` | Thông tin khách hàng, nhóm tuổi |
| `geography.csv` | Mã zip, thành phố, vùng |
| `inventory.csv` | Tình trạng tồn kho (stockout/overstock) |
| `web_traffic.csv` | Lưu lượng truy cập web theo ngày |
| `sales.csv` | Doanh thu và COGS tổng hợp theo ngày (dùng cho Phần 3) |
| `sample_submission.csv` | Mẫu file nộp bài (dùng cho Phần 3) |

---

## Cài đặt môi trường

```bash
pip install pandas numpy matplotlib seaborn scikit-learn
```

> Python 3.8+ được khuyến nghị.

---

## Thứ tự chạy khuyến nghị

Mỗi phần là notebook độc lập, có thể chạy theo bất kỳ thứ tự nào. Tuy nhiên nếu muốn hiểu toàn bộ pipeline:

```
Phần 1 (MCQ)  →  Phần 2 (EDA & Insights)  →  Phần 3 (Forecasting)
```

Xem README riêng của từng phần để biết hướng dẫn cụ thể về đường dẫn dữ liệu và cách chạy.

---

## Kết quả nổi bật

- **Phần 1:** 10/10 câu trắc nghiệm với code xác minh từng đáp án
- **Phần 2:** 4 business insights trực quan hoá bằng matplotlib/seaborn
- **Phần 3:** Validation MAE ~502,000 VND | R² = 0.826 trên tập 2021–2022
