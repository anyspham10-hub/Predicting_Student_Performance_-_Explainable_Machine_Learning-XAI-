# Predicting_Student_Performance_-_Explainable_Machine_Learning-XAI
## Giới thiệu
Dự án này xây dựng một mô hình học máy nhằm dự đoán điểm thi (`Exam_Score`) của học sinh/sinh viên dựa trên 19 yếu tố đặc trưng như thói quen học tập, môi trường gia đình và các hoạt động ngoại khóa. 

Điểm nổi bật của dự án là việc ứng dụng **Explainable AI (XAI)** thông qua thư viện **SHAP** để giải thích các dự đoán của mô hình. Điều này giúp các nhà giáo dục và phụ huynh hiểu rõ yếu tố nào đóng góp nhiều nhất vào kết quả học tập của từng học sinh.

## Mục tiêu
- Phân tích và khám phá dữ liệu (EDA) để tìm ra các mối tương quan.
- Huấn luyện và so sánh hiệu suất của 3 mô hình: Random Forest, XGBoost, và LightGBM.
- Sử dụng SHAP để giải thích mô hình ở cả cấp độ toàn cục (Global) và cục bộ (Local).

## Bộ dữ liệu
- **Nguồn:** Student Performance Factors Dataset
- **Kích thước:** 6,607 dòng, 20 cột.
- **Xử lý dữ liệu:** 
  - Điền khuyết (Imputation) bằng phương pháp `most_frequent` cho các biến phân loại (Categorical).
  - Mã hóa biến: `OrdinalEncoder` cho các biến có thứ tự (Low, Medium, High) và `LabelEncoder` cho biến nhị phân.

## Phương pháp & Công cụ
- **Ngôn ngữ:** Python 3
- **Thư viện:** Scikit-learn, XGBoost, LightGBM, SHAP, Pandas, Seaborn, Matplotlib.
- **Quy trình:** Tiền xử lý -> Chia tập Train/Test (80/20) -> Huấn luyện mô hình -> Đánh giá -> Giải thích mô hình.

## Kết quả
### Hiệu suất Mô hình
| Mô hình | RMSE | MAE | R² |
| :--- | :--- | :--- | :--- |
| Random Forest | 2.175 | 1.084 | 0.665 |
| XGBoost | 2.226 | 0.986 | 0.649 |
| **LightGBM** | **1.957** | **0.804** | **0.729** |

**Kết luận:** Mô hình **LightGBM** cho hiệu suất vượt trội nhất (R² = 0.729) và được chọn để phân tích XAI.

### Giải thích Mô hình với SHAP
- **Global Explainability:** Các yếu tố ảnh hưởng mạnh mẽ nhất đến điểm thi bao gồm:
  1. `Hours_Studied` (Số giờ học)
  2. `Attendance` (Tỷ lệ điểm danh)
  3. `Previous_Scores` (Điểm số trước đó)
  4. `Access_to_Resources` (Khả năng tiếp cận tài nguyên)
- **Local Explainability:** Biểu đồ Waterfall SHAP giải thích chi tiết lý do một học sinh cụ thể đạt mức điểm dự đoán nhất định (ví dụ: giờ học cao đóng góp tích cực, nhưng khuyết tật học tập làm giảm điểm).

## 💻 Cách chạy dự án
1. Clone repository này:
   ```bash
   git clone https://github.com/your-username/student-performance-xai.git

2. Cài đặt các thư viện cần thiết:

bash
pip install -r requirements.txt

3. Mở Jupyter Notebook và chạy file notebook.

## Cấu trúc thư mục
.

├── data/

│   └── StudentPerformanceFactors.csv

├── Predicting_Student_Performance_&_Explainable_Machine_Learning(XAI).ipynb

├── requirements.txt

├── README.md

└── .gitignore

## Author
Phạm Minh Ánh - anyspham2703@gmail.com

Trần Duy Quang - tranduyquang260@gmail.com

Đặng Bùi Minh Hiếu - danghieu05062006@gmail.com

MIT License

Copyright (c) 2024

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
