# 📊 Phần 2 — Phân tích Dữ liệu Khám phá (EDA & Business Insights)

**Notebook:** `vintelligent-datathon-2026-Part_2.ipynb`  
**Nhóm:** The Gridbreakers  
**Cuộc thi:** VinTelligent Datathon 2026

---

## Mô tả

Notebook này thực hiện **phân tích kinh doanh chuyên sâu** trên toàn bộ hệ sinh thái dữ liệu của cuộc thi, tổng hợp thành các **Business Insights có giá trị thực tiễn**:

| Insight | Chủ đề |
|---------|--------|
| **Insight 1** | Phân tích lợi nhuận theo loại khuyến mãi — phát hiện khuyến mãi "fixed" gây lỗ |
| **Insight 2** | Mất kết nối giữa Marketing (traffic) và Chuỗi cung ứng (stockout/overstock) |
| **Insight 3** | Rủi ro sau đơn hàng — COD có tỷ lệ huỷ cao nhất, phân tích lý do trả hàng |
| **Insight 4** | Phân tích Pareto vùng địa lý — tập trung doanh thu vào đâu |

---

## Dữ liệu đầu vào

Tất cả file CSV phải được đặt **cùng thư mục** với notebook:

```
orders.csv
order_items.csv
products.csv
promotions.csv
payments.csv
returns.csv
customers.csv
geography.csv
inventory.csv
web_traffic.csv
sales.csv
```

---

## Hướng dẫn thực thi

**Chạy Local (Jupyter Notebook / VS Code):**

1. Đặt tất cả file CSV vào cùng thư mục với notebook.
2. Mở `vintelligent-datathon-2026-Part_2.ipynb`.
3. Chạy **tuần tự từ trên xuống dưới** — `Cell 0` (Import & Load) phải chạy trước tất cả.
4. Notebook sẽ tự động export các biểu đồ ra file PNG:
   - `insight1_promo.png`
   - `insight2_supplychain.png`
   - `insight3_order_risk.png`
   - (và các biểu đồ insight khác)

> ⚠️ **Lưu ý quan trọng:** Cell đầu tiên load toàn bộ dữ liệu vào bộ nhớ. Không bỏ qua hoặc chạy lộn thứ tự — các cell sau phụ thuộc vào DataFrame được khởi tạo ở Cell 0.

---

## Output tạo ra

- Các biểu đồ phân tích (PNG) được lưu vào thư mục chạy
- In kết quả thống kê chi tiết trực tiếp ra console

---

## Thư viện cần thiết

```bash
pip install pandas numpy matplotlib seaborn
```
