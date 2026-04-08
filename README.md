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
- ***Configure Networking***: Chọn Default Switch (để máy ảo có internet)
- ***Connect Virtual Hard Disk***: Để mặc định (thường là 127GB, nhưng nó sẽ chỉ chiếm dung lượng thực tế dùng).
- ***Installation Options***: Chọn dòng Install an operating system from a bootable image file, sau đó nhấn **Browse** và chọn file ISO Ubuntu đã tải

<img width="877" height="666" alt="{6EF261FD-0BD7-420B-92D2-DEB2E1DEFCBF}" src="https://github.com/user-attachments/assets/a0e9490c-0db3-418a-a6fe-86f0688a5405" /></P>





