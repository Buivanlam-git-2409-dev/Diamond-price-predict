# 💎 Dự án Dự đoán Giá Kim cương (Diamond Price Prediction)

Dự án này sử dụng mô hình **Linear Regression (Hồi quy tuyến tính)** được xây dựng (custom implementation) để dự đoán giá của kim cương dựa trên các thuộc tính vật lý và chất lượng của chúng.

## 🚀 Các tính năng chính
- **Huấn luyện mô hình**: Quy trình xử lý dữ liệu, chuẩn hóa (Standardization) và huấn luyện mô hình bằng thuật toán Gradient Descent trong file Jupyter Notebook.
- **Ứng dụng Web**: Giao diện người dùng trực quan được xây dựng bằng **Streamlit**, cho phép người dùng nhập thông số và nhận kết quả dự đoán ngay lập tức.
- **Tiền xử lý dữ liệu**: Xử lý dữ liệu thô, loại bỏ các giá trị nhiễu (outliers), mã hóa các biến phân loại (Cut, Color, Clarity) và chuẩn hóa đặc trưng.

## 📁 Cấu trúc dự án
- `diamonds.csv`: Tập dữ liệu thô chứa thông tin của hơn 50,000 viên kim cương.
- `train.ipynb`: Notebook chứa toàn bộ quá trình phân tích dữ liệu (EDA), xử lý dữ liệu và huấn luyện mô hình.
- `weight.npz`: File lưu trữ các tham số mô hình đã huấn luyện (theta) cùng với giá trị trung bình (mean) và độ lệch chuẩn (std) để phục vụ dự đoán.
- `app.py`: Mã nguồn ứng dụng web giao diện Streamlit.
- `requirement.txt`: Hướng dẫn cài đặt và danh sách các thư viện cần thiết.
- `data.npz`: Dữ liệu đã qua xử lý được lưu trữ dưới dạng nén.

## 🛠 Hướng dẫn thiết lập (Setup)

1. **Tạo môi trường ảo (Conda):**
   ```bash
   conda create -n diamond_env python=3.8
   conda activate diamond_env
   ```

2. **Cài đặt các thư viện cần thiết:**
   ```bash
   python -m pip install --upgrade pip
   pip install -r requirement.txt
   ```

3. **Chạy ứng dụng Streamlit:**
   ```bash
   streamlit run app.py
   ```

4. **Khám phá Notebook (tùy chọn):**
   Nếu bạn muốn xem chi tiết quá trình huấn luyện:
   ```bash
   pip install jupyterlab
   jupyter lab
   ```

## 📊 Các thông số đầu vào
Ứng dụng sử dụng 9 đặc trưng kỹ thuật để dự đoán giá:
- **Carat**: Trọng lượng kim cương.
- **Cut**: Chất lượng chế tác (Fair, Good, Very Good, Premium, Ideal).
- **Color**: Cấp độ màu sắc (từ J đến D).
- **Clarity**: Độ trong suốt (I1, SI2, SI1, VS2, VS1, VVS2, VVS1, IF).
- **Depth & Table**: Các thông số tỷ lệ phần trăm cấu trúc.
- **X, Y, Z**: Kích thước vật lý (chiều dài, chiều rộng, chiều cao) tính bằng mm.
