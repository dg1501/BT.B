<img width="897" height="607" alt="{B5AA5D88-B4F7-478A-B91F-1CB5A47FA764}" src="https://github.com/user-attachments/assets/14cb17f8-96e1-4add-9da0-c3fdab7acad5" /># B. CÀI ĐẶT UBUNTU + DOCKER

### 1. CÀI ĐẶT HỆ ĐIỀU HÀNH UBUNTU 24.04.4 LTS

a) Kiểm tra Hyper - V

- Nhấn Win + R -> Gõ: **optionalfeatures** .</p>

Tích:

+ Hyper-V</p>

+ Hyper-V Platform</p>

+ Hyper-V Management Tools</p>

<img width="557" height="489" alt="{7C498F6A-92DF-4512-B451-D9107AC15513}" src="https://github.com/user-attachments/assets/7b877366-876e-4b82-aa20-491f13771e05" /></P>

### 2. TẢI UBUNTU TRÊN HYPER-V

a) Dowload Ubuntu

- Download file iso để cài đặt.</p>

<img width="317" height="58" alt="{77EA4997-A725-47CB-BCB8-A145711D565E}" src="https://github.com/user-attachments/assets/a82c134f-b72d-4cad-9301-dde850549ce0" /></p>

b) Tạo máy ảo trong Hyper-V

Bước 1: Mở Hyper-V Manager

New → Virtual Machine

<img width="477" height="195" alt="{E1114C24-C6A6-4639-9118-B52EA03C7D4F}" src="https://github.com/user-attachments/assets/48988569-3505-4ff9-b3f0-a705e55e47bc" /></p>

Cấu hình:

- ***Name***: Ubuntu
- ***Specify Generation***: Chọn Generation 2 (Bắt buộc để hỗ trợ tốt nhất cho Ubuntu mới).
- ***Assign Memory***: Nhập 2048 MB (2GB). Nên tích chọn Use Dynamic Memory
- ***Configure Networking***: Tạm chọn Default Switch (để máy ảo có internet)
- ***Connect Virtual Hard Disk***: Để mặc định (thường là 127GB, nhưng nó sẽ chỉ chiếm dung lượng thực tế dùng).
- ***Installation Options***: Chọn dòng Install an operating system from a bootable image file, sau đó nhấn **Browse** và chọn file ISO Ubuntu đã tải

<img width="877" height="666" alt="{6EF261FD-0BD7-420B-92D2-DEB2E1DEFCBF}" src="https://github.com/user-attachments/assets/a0e9490c-0db3-418a-a6fe-86f0688a5405" /></P>

Bước 2: Cấu hình mạng (Quan trọng nhất)

- Nếu để **Default Switch** → KHÔNG SSH được từ Windows

- Phải tạo External Switch.

- Trong Hyper - V: `Virtual Switch Manager → New → External`

<img width="1156" height="504" alt="{985846F6-C9E5-4CF8-A5CF-5B65A7713240}" src="https://github.com/user-attachments/assets/06c2cbaa-2060-4c5a-a536-32d9a428a64d" /></p>

- Chọn card mạng thật (WiFi hoặc Ethernet)
  
- Name: ExternalSwitch
  
- Tick: Allow management OS to share this network

<img width="709" height="508" alt="{E989B2F3-EA47-42F8-B7EF-3F27423D1048}" src="https://github.com/user-attachments/assets/bf6883f1-ba6b-43b0-8fc6-8decc9e63136" /></p>

Bước 3: Gán switch cho VM

- VM → Settings → Network Adapter
  
- Chọn: **ExternalSwitch**

<img width="840" height="340" alt="{3128303B-7AB8-48AF-BBE9-691078C80BDC}" src="https://github.com/user-attachments/assets/9f10bc34-9847-400c-8925-2cd83e3e9cde" /></p>

Bước 4: Cài đặt Ubuntu

<img width="741" height="344" alt="image" src="https://github.com/user-attachments/assets/6cd38ff6-3d5c-4455-a58c-1e70266962ae" /></p>

- Chọn **Try or Install Ubuntu Server và nhấn Enter**

<img width="1279" height="846" alt="image" src="https://github.com/user-attachments/assets/fff84232-a1ce-4924-aad2-82cf9b615587" /></p>

- Chọn ngôn ngữ

<img width="1133" height="539" alt="image" src="https://github.com/user-attachments/assets/cd806f78-a2e7-478b-bf4a-dd76207afa7f" /></p>

- Tích vào ô Install OpenSSH server
  
<img width="1031" height="308" alt="image" src="https://github.com/user-attachments/assets/b7f26205-b22b-45c0-afbf-7d7a87bac43e" /></p>

### SAU KHI THỰC HIỆN 1 LOẠT CÁC THAO TÁC HOẠT ĐỘNG TA ĐƯỢC GIAO DIỆN UBUNTU NHƯ HÌNH DƯỚI

<img width="1315" height="354" alt="image" src="https://github.com/user-attachments/assets/f1795bba-3216-4cc8-a6e4-6a4afa1f370f" />

### 3. CẤU HÌNH MẠNG TRONG UBUNTU

a) Lấy IP Ubuntu

- Trước khi lấy Ip tiến hành kiểm tra SSH đã hoạt động chưa bằng lệnh `sudo systemctl status ssh`

<img width="894" height="399" alt="image" src="https://github.com/user-attachments/assets/986494dd-9836-474d-a586-cbcccc1a2fb6" /></p>

- Sử dụng lệnh `ip -4 addr ` để lấy ip

<img width="875" height="242" alt="{82C47E21-F2DF-49EC-9C6C-CA67BD54F51F}" src="https://github.com/user-attachments/assets/06455bb4-fd99-4472-ab32-33d6d8a381ec" /></p>

b) SSH từ Windows

- Mở CMD Windows: `ssh duong@172.20.155.141`

<img width="1124" height="650" alt="{81F1EFFC-AC63-4935-A0B8-EC60F564D40F}" src="https://github.com/user-attachments/assets/9091c104-f749-48c1-8637-e62225ae9435" /></p>

### 4. TÌM HIỂU CÁC LỆNH CƠ BẢN CỦA UBUNTU

🎯 Mục tiêu
Tìm hiểu và thực hành các lệnh cơ bản trong Ubuntu để:
- Quản lý file và thư mục
- Chỉnh sửa nội dung file
- Kiểm tra thông tin hệ thống

---

#### 1️⃣ Lệnh ls - Liệt kê file/thư mục

- Hiển thị danh sách file và thư mục trong thư mục hiện tại.

`ls`

<img width="776" height="146" alt="{42B6E38A-ED84-4891-993A-A52C949081DF}" src="https://github.com/user-attachments/assets/e98c2c34-b5d1-4409-acaf-b833a4ab8b7b" /></p>

#### 2️⃣ Lệnh mkdir - Tạo thư mục

- Dùng để tạo thư mục mới.

`mkdir tenThuMuc`

<img width="901" height="199" alt="{E83FFA1E-DCA8-4B27-8F7E-67178560E906}" src="https://github.com/user-attachments/assets/ba3b64db-fab8-41af-9f14-3ca45b7adc5c" /></p>

#### 3️⃣ Lệnh cd - Chuyển thư mục

- Dùng để di chuyển giữa các thư mục.

`cd duong_dan`

<img width="325" height="89" alt="{1831B266-D6BD-4F4B-9375-7C1DD67BD1F5}" src="https://github.com/user-attachments/assets/861121aa-9dc1-4709-8787-3c8e935d6a1f" /></p>

#### 4️⃣ Lệnh cp - Sao chép file

- Sao chép file từ vị trí này sang vị trí khác.

`cp file_nguon file_dich`

#### 5️⃣ Lệnh chmod - Thay đổi quyền file

- Thay đổi quyền truy cập file.

`sudo chmod xxx filename`

🧠 Giải thích quyền
- Số	Ý nghĩa</p>
- 7	đọc + ghi + thực thi</p>
- 6	đọc + ghi</p>
- 5	đọc + thực thi</p>

<img width="881" height="516" alt="{4C029A4A-3C70-45D8-AF8B-CBDDCCA12751}" src="https://github.com/user-attachments/assets/1bb2273b-c156-4b2b-8e27-6583c65a9ce4" /></p>

#### 6️⃣ Lệnh nano - Chỉnh sửa file

- Mở file để chỉnh sửa nội dung.

`sudo nano tenfile`

⌨️ Phím tắt trong nano
- Phím	Chức năng
- Ctrl + O	Lưu file
- Ctrl + X	Thoát

<img width="1106" height="649" alt="{A426DE10-C6D0-4D84-B23B-BAD808E6D6C9}" src="https://github.com/user-attachments/assets/5542674c-b541-46bf-837f-4301abac9360" /></p>

#### 7️⃣ Lệnh ip -4 addr - Xem địa chỉ IP

- Hiển thị địa chỉ IP của máy Ubuntu.

`ip -4 addr`

<img width="859" height="163" alt="image" src="https://github.com/user-attachments/assets/d6c7b90c-f6f3-4216-86de-b26eb5debcfc" /></p>

### 5. CÀI ĐẶT DOCKER CHO UBUNTU

- Docker là nền tảng giúp đóng gói ứng dụng và các thành phần phụ thuộc vào một container, giúp chạy ứng dụng nhất quán trên nhiều môi trường khác nhau.

🚀 Bước 1: Cập nhật hệ thống

`sudo apt update`

`sudo apt upgrade -y`

<img width="696" height="279" alt="{1E903455-A871-4A16-9180-7797AD501A30}" src="https://github.com/user-attachments/assets/d613c7c5-2d8f-4e4d-ac05-aa3e79529beb" /></p>

🚀 Bước 2: Cài các gói cần thiết

`sudo apt install -y ca-certificates curl gnupg`

🚀 Bước 3: Cài Docker

`curl -fsSL https://get.docker.com | sh`

<img width="847" height="806" alt="{94F87DE7-E2B0-4FF5-9545-7D460260E8E3}" src="https://github.com/user-attachments/assets/bd0b1bc5-bfc0-4f9a-8cab-903765542ed2" /></p>

### 6. Kiểm tra phiên bản docker vừa cài đặt, kiểm tra phiên bản của docker compose

<img width="821" height="231" alt="{262B0163-0449-4F54-A446-459DD89EC322}" src="https://github.com/user-attachments/assets/5d02e8d5-586a-4291-af5d-0676a6d9102b" /></p>

📖 Giải thích
`docker --version`: kiểm tra phiên bản Docker Engine</p>

`docker compose version`: kiểm tra Docker Compose (dùng để chạy nhiều container)</p>

### 7. Cấu hình để docker chạy mà không cần tiền tố sudo

📖 Lý thuyết

- Mặc định Docker cần quyền root (sudo).</p>

- Ta thêm user vào nhóm docker để chạy bình thường.</p>

`sudo usermod -aG docker $USER`
`newgrp docker`

- Kiểm tra</p>

`docker run hello-world`

<img width="897" height="607" alt="{B5AA5D88-B4F7-478A-B91F-1CB5A47FA764}" src="https://github.com/user-attachments/assets/2d1d24f0-1386-4278-a421-6c0d9a8f75f7" /></p>

