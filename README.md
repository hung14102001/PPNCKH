# Đề tài: Chuyển đổi hình ảnh khuôn mặt từ 2D sang 3D
## Mục đích
Chuyển đổi hình ảnh khuôn mặt từ 2D sang mô hình 3D bao gồm cả biểu lộ cảm xúc khuôn mặt, nhằm sử dụng cho các ứng dụng tái tạo khuôn mặt hoặc tạo hình đại diện là bài toán khó. Trong báo cáo này, chúng tôi tìm hiểu và trình bày về mô hình DECA (Detailed Expression Capture and Animation) giúp tái tạo mô hình khuôn mặt 3D từ một ảnh 2D, đồng thời xây dựng các animation về biểu cảm khuôn mặt 3D, nhằm tạo ra một khuôn mặt giống như thật. Mô hình có độ chính xác trên 91%. Các bản tái tạo của DECA vượt trội hơn so với các phương pháp cũ trong các tư thế đầu, biểu cảm, độ phân giải hình ảnh, điều kiện ánh sáng…

## Kiến trúc tổng thể
<p align="center">   
    <img src="Kiến trúc hệ thống.drawio.png">
</p>

- Lấy ảnh người dùng vừa chụp rồi khoanh vùng khuôn mặt sử dụng thư viện opencv và mediapipe của python.

- Lấy ảnh đã qua xử lý rồi đưa vào server Machine Learning

- Sử dụng hình ảnh được đưa lên để chuyển sang mô hình 3D và gửi lại người dùng

## tiến độ
- tên dự án, mục đích của dự án, ảnh kiến trúc tổng thể 50%
- yêu cầu về môi trường, hệ điều hành, phần cứng tối thiểu 35%
- cách cài đặt môi trường và thư viện 70%
- cách build và chạy dự án 30 %
- cách chạy unit-test 0%
- các lỗi hay gặp 40%


## Yêu cầu về môi trường, hệ điều hành phần cứng tối thiểu 
### Môi trường
* Python 3.7 (numpy, skimage, scipy, opencv)  
* PyTorch >= 1.6 (pytorch3d)  
* face-alignment
* Mediapipe 
* Các thư viện khác có trong file [requirements.txt](requirements.txt)
  
  Cách cài đặt
  ```bash
  pip install -r requirements.txt
  ```
  Or use virtual environment by runing 
  ```bash
  bash install_conda.sh
  ```
### Hệ điều hành
- Dự án chạy được trên Ubuntu 20.04
- Đối với Windows có thể sử dụng máy ảo VMware hoặc Oracle VM VirtualBox
### Phần cứng tối thiểu
- GPU của Nvidia

## Cách chạy Demo
Tải repository:
  ```bash
  git clone https://github.com/YadiraF/DECA
  cd DECA
  ```  
Tái tạo
  ```bash
  python demos/demo_reconstruct.py -i TestSamples/examples --saveDepth True --saveObj True
  ```
Chuyển đổi biểu cảm
  ```bash
  python demos/demo_transfer.py
  ```

  ```bash
  python demos/demo_teaser.py 
  ```
## Cách chạy unit test

## Các lỗi hay gặp
- Cài ubuntu (main Asus)
- Phần cứng không đủ yêu cầu (mua thêm phần cứng :D)
- Cài drive nvidia trên ubuntu( main Asus)
- ngày tàn
