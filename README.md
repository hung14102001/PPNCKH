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
- tên dự án, mục đích của dự án, ảnh kiến trúc tổng thể 80%
- yêu cầu về môi trường, hệ điều hành, phần cứng tối thiểu 85%
- cách cài đặt môi trường và thư viện 70%
- cách build và chạy dự án 30 %
- cách chạy unit-test 0%
- các lỗi hay gặp 40%


## Yêu cầu về môi trường, hệ điều hành phần cứng tối thiểu 

### Phần cứng tối thiểu
- GPU của Nvidia 

  Dùng lệnh sau đây trên Terminal để kiểm tra 
```bash 
nvidia-smi
```
- Ram tối thiểu 8GB
- CPU 4 nhân 8 luồng, bus từ 2GHz trở lên 
### Hệ điều hành
- Dự án chạy được trên Ubuntu 20.04
- Đối với Windows có thể sử dụng máy ảo [VMware](https://download.com.vn/vmware-workstation-8587) hoặc [Oracle VM VirtualBox](https://www.virtualbox.org/)

### Môi trường
* [Python 3.7](https://www.python.org/downloads/) trở lên (numpy, skimage, scipy, opencv)  
* Các thư viện khác có trong file [requirements.txt](requirements.txt)
  
  Cách cài đặt
  ```bash
  pip install -r requirements.txt
  ```
  Sử dụng lệnh sau nếu dùng máy ảo 
  ```bash
  bash install_conda.sh
  ```



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
- Cài ubuntu khi chế độ SATA operation là RAID on thì không cài được Ubuntu.

  Cách khắc phục:

  Khi máy khởi động vào trong bios sang System configuration, SATA operation chuyển sang chế độ AHCI. Tham khảo thêm [tại đây](https://www.youtube.com/watch?v=wDrCaAdGuMk).
- Cài drive nvidia trên ubuntu có thể bị lỗi

  Cách khắc phục:

  Tắt chế độ khởi động an toàn ( Disable Secure Boot Mode) trong BIOS. Tham khảo thêm [tại đây](https://www.youtube.com/watch?v=brXcxmdWU9Q)
- Thiếu bộ nhớ


