## Cấu trúc thư mục yêu cầu

Bạn cần đặt các file dữ liệu vào đúng cấu trúc đường dẫn như sau (hoặc cấu hình lại biến `DATA_DIR` trong notebook):

```text
├── input/
│   └── competitions/
│       └── datathon-2026-round-1/
│           ├── sales.csv
│           └── sample_submission.csv
├── vintelligent-datathon-2026-v-ng-s-lo-i.ipynb   # File mã nguồn gốc
└── README.md

## Hướng dẫn thực thi

Trên Kaggle (Khuyến nghị):
- Tải notebook lên môi trường Kaggle.
- Chọn Run All để chạy tuần tự toàn bộ các cell.

Chạy Local (Jupyter Notebook / VS Code):
- Sửa lại đường dẫn DATA_DIR tại Section 1 thành đường dẫn chứa dữ liệu local của bạn.
- Chạy tuần tự từ trên xuống dưới.