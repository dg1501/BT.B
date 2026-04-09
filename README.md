## B. CÀI ĐẶT UBUNTU + DOCKER

### 1. Cài đặt hệ điều hành Ubuntu 24.04.4 LTS

a) Kiểm tra Hyper - V

- Nhấn Win + R -> Gõ: **optionalfeatures** .</p>

Tích:

+ Hyper-V</p>

+ Hyper-V Platform</p>

+ Hyper-V Management Tools</p>

<img width="557" height="489" alt="{7C498F6A-92DF-4512-B451-D9107AC15513}" src="https://github.com/user-attachments/assets/7b877366-876e-4b82-aa20-491f13771e05" /></P>

### 2. Tải Ubuntu trên Hyper - V

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

### 3. Cấu hình mạng trong Ubuntu

a) Lấy IP Ubuntu

- Trước khi lấy Ip tiến hành kiểm tra SSH đã hoạt động chưa bằng lệnh `sudo systemctl status ssh`

<img width="894" height="399" alt="image" src="https://github.com/user-attachments/assets/986494dd-9836-474d-a586-cbcccc1a2fb6" /></p>

- Sử dụng lệnh `ip -4 addr ` để lấy ip

<img width="875" height="242" alt="{82C47E21-F2DF-49EC-9C6C-CA67BD54F51F}" src="https://github.com/user-attachments/assets/06455bb4-fd99-4472-ab32-33d6d8a381ec" /></p>

b) SSH từ Windows

- Mở CMD Windows: `ssh duong@172.20.155.141`

<img width="1124" height="650" alt="{81F1EFFC-AC63-4935-A0B8-EC60F564D40F}" src="https://github.com/user-attachments/assets/9091c104-f749-48c1-8637-e62225ae9435" /></p>

### 4. Tìm hiểu các lệnh cơ bản của ubuntu

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


