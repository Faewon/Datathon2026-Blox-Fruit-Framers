# 📊 Phần 2 — Phân tích Dữ liệu Kinh doanh (EDA & Business Insights)

**Notebook:** `vintelligent-datathon-2026-Part_2.ipynb`  
**Nhóm:** Blox Fruit Farmers  
**Cuộc thi:** VinTelligent Datathon 2026

---

## Mô tả

Notebook này thực hiện **phân tích kinh doanh chuyên sâu** theo khung 4 tầng (Descriptive → Diagnostic → Predictive → Prescriptive) trên toàn bộ hệ sinh thái dữ liệu, tổng hợp thành **5 Business Insights + 1 Bonus Analysis**.

| # | Insight | Vấn đề cốt lõi |
|---|---------|----------------|
| **1** | Khuyến mãi Fixed bán dưới giá vốn | COGS > unit_price — lỗi catalog, thiệt hại ~235 triệu VND |
| **2** | Đứt gãy Marketing & Supply Chain | Traffic ↔ stockout r=0.83, nhưng traffic ↔ overstock r=0.08 |
| **3** | Thất thoát doanh thu sau đơn hàng | COD huỷ 16% (gấp đôi benchmark), 73% hoàn trả do lỗi sản phẩm |
| **4** | Phân bổ doanh thu theo địa lý | East chiếm 46.5%; cần 67% thành phố để đạt 80% doanh thu |
| **5** | Phân khúc khách hàng RFM | 40% khách At Risk, Champions chi tiêu gấp 10.4× At Risk |
| **Bonus** | Kênh tăng trưởng & xu hướng doanh thu | Organic search #1, Mobile vượt Desktop, AOV đồng đều mọi kênh |

---

## Dữ liệu đầu vào

Tất cả file CSV cần đặt **cùng thư mục** với notebook (hoặc upload vào Google Colab):

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

### Chạy trên Google Colab (Khuyến nghị)

1. Upload notebook lên Google Colab.
2. Upload toàn bộ file CSV vào mục **Files** (biểu tượng 📁 bên trái) — **không cần chạy cell import** ở đầu notebook (cell đó dành cho upload thủ công, rất chậm).
3. Chọn **Runtime → Run all** để chạy toàn bộ.

> ⚠️ Cell đầu tiên (block `from google.colab import files`) bị comment sẵn — **không bỏ comment**, chỉ cần upload file vào Files panel là đủ.

### Chạy Local (Jupyter Notebook / VS Code)

1. Đặt tất cả file CSV vào cùng thư mục với notebook.
2. Mở `EDA_5insights__1_.ipynb`.
3. Chạy **tuần tự từ trên xuống dưới** — **Cell 0 (Import & Load) phải chạy trước tất cả**, các cell sau phụ thuộc vào các DataFrame được khởi tạo ở bước này.

---

## Các bước thực hiện

| Cell | Nội dung |
|------|----------|
| **Cell 0** | Import thư viện, cấu hình style, load toàn bộ 11 file CSV, tính `ord_rev` (doanh thu từng đơn — dùng lại ở mọi insight) |
| **Insight 1** | Merge `order_items` + `products` + `promotions`, so sánh lợi nhuận ròng theo loại KM, vẽ biểu đồ net profit & Unit Price vs COGS |
| **Insight 2** | Tổng hợp `inventory` + `web_traffic` theo tháng 2022, tính tương quan Traffic↔Stockout/Overstock, vẽ dual-axis chart |
| **Insight 3** | Phân tích tỷ lệ huỷ đơn theo phương thức thanh toán + phân tích lý do hoàn trả theo category, vẽ biểu đồ 2×2 |
| **Insight 4** | Tính doanh thu theo thành phố & vùng, vẽ Pareto chart + donut vùng |
| **Insight 5** | Xây dựng RFM model (Recency/Frequency/Monetary), phân loại khách hàng thành 4 segment, vẽ biểu đồ quy mô & chi tiêu |
| **Bonus** | Phân tích doanh thu theo `order_source` & `device_type`, vẽ xu hướng Revenue + Gross Margin theo tháng |

---

## Output tạo ra

Notebook tự động lưu các biểu đồ vào thư mục đang chạy:

| File | Nội dung |
|------|----------|
| `insight1_promo.png` | Lợi nhuận ròng & Unit Price vs COGS theo loại KM |
| `insight2_supplychain.png` | Traffic vs Stockout/Overstock 2022 |
| `insight3_order_risk.png` | Tỷ lệ huỷ COD, phân bổ trạng thái đơn, lý do hoàn trả |
| `insight5_geo.png` | Pareto doanh thu thành phố & tỷ trọng theo vùng |
| `insight6_rfm.png` | Quy mô & chi tiêu TB theo RFM segment |
| `bonus_channel_trend.png` | Doanh thu theo kênh, thiết bị & xu hướng tháng |

---

## Thư viện cần thiết

```bash
pip install pandas numpy matplotlib seaborn
```
