Application
📌 Mục đích
Chương trình này thực hiện việc xử lý ảnh từ thư mục exercise bằng cách:

Hoán đổi thứ tự kênh màu RGB một cách ngẫu nhiên.

Áp dụng ngẫu nhiên một trong ba phép biến đổi ảnh:

Fast Fourier Transform (FFT)

Butterworth Lowpass Filter + Min Filter

Butterworth Highpass Filter + Max Filter

Lưu ảnh đã xử lý vào thư mục output_4 và hiển thị ảnh.

🧪 Các phép biến đổi ảnh
1. Fast Fourier Transform (FFT)
Chuyển ảnh sang miền tần số.

Hiển thị phổ biên độ (magnitude spectrum).

2. Butterworth Lowpass Filter
Lọc các thành phần tần số cao, giữ lại chi tiết thấp (mịn ảnh).

Sau đó áp dụng Min Filter để giảm nhiễu hoặc làm mờ.

3. Butterworth Highpass Filter
Lọc các thành phần tần số thấp, giữ lại chi tiết cao (làm rõ biên cạnh).

Sau đó áp dụng Max Filter để làm rõ biên thêm nữa.