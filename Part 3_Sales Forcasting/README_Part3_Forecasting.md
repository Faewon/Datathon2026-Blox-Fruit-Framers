# 🏆 Phần 3 — Dự báo Doanh thu (Sales Forecasting — V3 Optimized)

**Notebook:** `vintelligent-datathon-2026-Part_3.ipynb`  
**Nhóm:** The Gridbreakers  
**Cuộc thi:** VinTelligent Datathon 2026

---

## Mô tả

Notebook này xây dựng mô hình **dự báo doanh thu (Revenue) và giá vốn (COGS)** theo ngày bằng thuật toán **Gradient Boosting Regressor** với chiến lược feature engineering tối ưu hóa (V3):

- **Short-term lags** (1d, 2d, 3d) — tương quan cao nhất (0.87, 0.74, 0.62)
- **EMA** (Exponential Moving Average) — phản ứng nhanh hơn SMA
- **Seasonal profile** (month × day) + Day-of-week × Month factor
- **GBR** với hyperparameters tinh chỉnh: 500 trees, learning_rate=0.03

**Kết quả validation (2021–2022):** MAE ~502,000 VND | R² = 0.826

---

## Cấu trúc thư mục yêu cầu

Bạn cần đặt các file dữ liệu vào đúng cấu trúc đường dẫn như sau (hoặc cấu hình lại biến `DATA_DIR` trong notebook):

```text
├── input/
│   └── competitions/
│       └── datathon-2026-round-1/
│           ├── sales.csv
│           └── sample_submission.csv
├── vintelligent-datathon-2026-Part_3.ipynb
└── README.md
```

---

## Hướng dẫn thực thi

**Trên Kaggle (Khuyến nghị):**

1. Tải notebook lên môi trường Kaggle.
2. Gắn dataset `datathon-2026-round-1` vào notebook.
3. Chọn **Run All** để chạy tuần tự toàn bộ các cell.

**Chạy Local (Jupyter Notebook / VS Code):**

1. Sửa lại biến `DATA_DIR` tại **Section 1** thành đường dẫn chứa dữ liệu local của bạn:
   ```python
   DATA_DIR = '/đường/dẫn/local/của/bạn/'
   ```
2. Đảm bảo thư mục đó chứa đủ `sales.csv` và `sample_submission.csv`.
3. Chạy tuần tự từ trên xuống dưới theo đúng thứ tự các section.

---

## Các bước thực hiện theo Section

| Section | Nội dung |
|---------|----------|
| **1. Import & Config** | Load thư viện, cấu hình `DATA_DIR`, đặt random seed |
| **2. Load Data** | Đọc `sales.csv` và `sample_submission.csv` |
| **3. EDA** | Vẽ biểu đồ doanh thu theo ngày/năm/tháng, phân tích tương quan lag |
| **4. Feature Engineering** | Tạo 60+ features: calendar, lag, rolling, EMA, seasonal profile |
| **5. Define Features** | Khai báo danh sách `FEATURES` và `TARGET` |
| **6. Validation** | Time-series split: Train 2015–2020 / Validate 2021–2022 |
| **7. Training & Evaluation** | Huấn luyện GBR cho Revenue và COGS, in MAE/RMSE/R² |
| **8. Final Training** | Retrain trên toàn bộ dữ liệu (2015–2022) |
| **9. Prediction** | Dự báo cho tập test, xuất `submission.csv` |

---

## Output tạo ra

- `revenue_overview.png` — Biểu đồ EDA tổng quan doanh thu
- `validation_plot.png` — Biểu đồ Actual vs Predicted (2021–2022)
- `submission.csv` — File kết quả nộp cuộc thi

---

## Thư viện cần thiết

```bash
pip install pandas numpy matplotlib scikit-learn
```
