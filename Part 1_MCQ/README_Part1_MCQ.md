# 📋 Phần 1 — Câu hỏi Trắc nghiệm (MCQ)

**Notebook:** `vintelligent_datathon_2026_MCQ.ipynb`  
**Nhóm:** Blox Fruit Farmers
**Cuộc thi:** VinTelligent Datathon 2026

---

## Mô tả

Notebook này giải toàn bộ **10 câu hỏi trắc nghiệm** bằng cách tính toán trực tiếp từ dữ liệu thô, không đoán mò — mỗi câu đều có code xác minh kết quả.

---

## Dữ liệu đầu vào

Tất cả các file CSV cần được đặt **cùng thư mục** với notebook (hoặc cập nhật đường dẫn trong code):

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
2. Mở `vintelligent_datathon_2026_MCQ.ipynb`.
3. Chọn **Run All** (hoặc `Kernel → Restart & Run All`) để chạy tuần tự từ trên xuống dưới.
4. Mỗi cell in ra kết quả tính toán và xác nhận đáp án đúng.

> ⚠️ Không cần cấu hình thêm — notebook dùng đường dẫn tương đối, chỉ cần CSV nằm cùng thư mục.

---

## Tóm tắt đáp án

| Câu | Câu hỏi | Đáp án | Giá trị |
|-----|---------|--------|---------|
| Q1 | Trung vị số ngày giữa hai lần mua liên tiếp | **C) 144 ngày** | Median gap = 144.0 ngày |
| Q2 | Phân khúc có tỷ suất lợi nhuận gộp cao nhất | **D) Standard** | Gross margin ~31.3% |
| Q3 | Lý do trả hàng phổ biến nhất (Streetwear) | **B) wrong_size** | 7,626 lần |
| Q4 | Nguồn traffic có bounce_rate thấp nhất | **C) email_campaign** | avg bounce = 0.004458 |
| Q5 | Tỷ lệ dòng order_items có khuyến mãi | **C) 39%** | Chính xác 38.7% |
| Q6 | Nhóm tuổi có số đơn trung bình cao nhất | **A) 55+** | avg ~5.41 đơn/khách |
| Q7 | Vùng có tổng doanh thu cao nhất | **C) East** | ~7.29 tỷ VND |
| Q8 | Phương thức thanh toán phổ biến nhất (đơn bị huỷ) | **A) credit_card** | 28,452 đơn |
| Q9 | Kích thước có tỷ lệ trả hàng cao nhất | **A) S** | return rate = 5.65% |
| Q10 | Kế hoạch trả góp có giá trị TB cao nhất | **C) 6 kỳ** | avg ~24,446 VND |

---

## Thư viện cần thiết

```bash
pip install pandas numpy
```
