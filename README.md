## B. CÀI ĐẶT UBUNTU + DOCKER

1. Cài đặt hệ điều hành Ubuntu 24.04.4 LTS

a) Kiểm tra Hyper - V

- Nhấn Win + R -> Gõ: **optionalfeatures** .</p>

Tích:

+ Hyper-V</p>

+ Hyper-V Platform</p>

+ Hyper-V Management Tools</p>

<img width="557" height="489" alt="{7C498F6A-92DF-4512-B451-D9107AC15513}" src="https://github.com/user-attachments/assets/7b877366-876e-4b82-aa20-491f13771e05" /></P>

2. Tải Ubuntu trên Hyper - V

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

- Chọn Try or Install Ubuntu Server và nhấn Enter

<img width="1279" height="846" alt="image" src="https://github.com/user-attachments/assets/fff84232-a1ce-4924-aad2-82cf9b615587" /></p>

- Chọn ngôn ngữ

<img width="1133" height="539" alt="image" src="https://github.com/user-attachments/assets/cd806f78-a2e7-478b-bf4a-dd76207afa7f" /></p>

- Tích vào ô Install OpenSSH server
-  
<img width="1031" height="308" alt="image" src="https://github.com/user-attachments/assets/b7f26205-b22b-45c0-afbf-7d7a87bac43e" /></p>

### SAU KHI THỰC HIỆN 1 LOẠT CÁC THAO TÁC HOẠT ĐỘNG TA ĐƯỢC GIAO DIỆN UBUNTU NHƯ HÌNH DƯỚI

<img width="1315" height="354" alt="image" src="https://github.com/user-attachments/assets/f1795bba-3216-4cc8-a6e4-6a4afa1f370f" />

3. Cấu hình mạng trong Ubuntu

a) Lấy IP Ubuntu

- Sử dụng lệnh `ip -4 addr `




