1. Cắt ảnh
    data = iio.imread('fruit.jpg') đọc file    

    bmg = data[800:1200, 570:980] : cắt ảnh 

    print(data.shape) : in ảnh với kích thước gốc

2. Tịnh tiến đơn 
    data = iio.imread('fruit.jpg') đọc file 

    bdata = np.roll(data, shift=(100, 25), axis=(0, 1)): Dịch chuyển ảnh xuống 100pixel và sang phải 25px

3. Zoom ảnh
    data = iio.imread('fruit.jpg') đọc file    

    nd.zoom(data, 2): phóng to ảnh lên 2 lần theo mọi chiều.

    nd.zoom(data, (2, 2, 1)): phóng to 2 lần chiều cao, 2 lần chiều rộng, giữ nguyên kênh màu.

    nd.zoom(data, (0.5, 0.9, 1)): thu nhỏ ảnh: 50% chiều cao, 90% chiều rộng, không đổi kênh màu.

4. Xoay ảnh

    data = iio.imread('fruit.jpg') đọc file    

    nd.rotate(data, 20): xoay ảnh 20 độ, kích thước ảnh có thể thay đổi để chứa toàn bộ ảnh sau xoay.

    reshape=False: xoay ảnh nhưng giữ nguyên kích thước gốc, nên có thể bị cắt một phần ảnh.

5. Giãn nhị phân (binary dilation)

    data = iio.imread('world.jpg', mode='F') đọc file    

    Chuyển ảnh về thang xám.

    binary_dilation: làm ảnh trắng hơn, mở rộng vùng trắng trong ảnh nhị phân.

    iterations=3: lặp lại quá trình giãn 3 lần → vùng trắng mở rộng nhiều hơn.

6. Biến dạng ảnh bằng nhiễu ngẫu nhiên  
    data = iio.imread('world.jpg', mode='F') đọc file   

    Dùng map_coordinates để áp dụng biến dạng ngẫu nhiên.

    q: tạo ra nhiễu ngẫu nhiên trong khoảng ±d.

    mp: các điểm ảnh được biến đổi theo nhiễu → tạo hiệu ứng biến dạng sóng, rung lắc ảnh.

7. Biến đổi hình học với hàm tùy chỉnh
    data = iio.imread('world.jpg', mode='F') đọc file   
    
    Hàm GeoFun tạo hiệu ứng biến dạng sóng bằng hàm cos().

    geometric_transform: áp dụng phép biến đổi hình học lên toàn ảnh bằng cách ánh xạ điểm đầu ra → điểm đầu vào.

    Kết quả là ảnh bị biến dạng lượn sóng theo cả chiều dọc và ngang.