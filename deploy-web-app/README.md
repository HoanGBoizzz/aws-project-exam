Bước 1: Tạo tài khoản AWS
  
  -Đăng ký tài khoản AWS: Nếu bạn chưa có tài khoản, hãy truy cập AWS và tạo tài khoản.

Bước 2: Tạo Instance EC2
  
  -Đăng nhập vào AWS Management Console.
  
  -Chọn EC2 từ bảng điều khiển.
  
  -Nhấn vào “Launch Instance” để tạo một phiên bản mới.
  
  -Chọn Amazon Machine Image (AMI): Chọn AMI Windows Server (ví dụ: Windows Server 2022).
  
  -Chọn Instance Type: Chọn loại instance (ví dụ: t2.micro) cho kế hoạch miễn phí.
  
  -Cấu hình Instance: Nhấn “Next: Configure Instance Details” và để cấu hình mặc định.
  
  -Thêm Storage: nThêm dung lượng nếu cần, mặc định thường đủ cho ứng dụng nhỏ.
  
  -Thêm Tags (Tùy chọn): Bạn có thể thêm tags để quản lý dễ hơn.
  
  -Cấu hình Security Group.
  
  -Tạo một security group mới hoặc sử dụng nhóm hiện tại, đảm bảo cho phép các cổng sau: 
  
  +HTTP: Port 80
  +HTTPS: Port 443
  +RDP: Port 3389 (để kết nối vào server)
  
  -Review and Launch: Xem lại cấu hình và nhấn “Launch”.
  
  -Tạo Key Pair: Tạo key pair mới hoặc sử dụng key pair hiện tại để truy cập vào instance.

Bước 3: Kết nối tới Instance EC2
  
  -Mở Remote Desktop Connection (RDP): Trên máy tính của bạn, tìm kiếm "Remote Desktop Connection" và mở nó.
  
  -Kết nối vào instance:
    
    +Nhập địa chỉ IP công cộng của instance (có thể tìm thấy trong bảng điều khiển EC2).
    +Nhấn "Connect".
  
  -Nhập thông tin đăng nhập:
    
    +Sử dụng file .pem để tạo mật khẩu cho tài khoản Administrator (nếu cần).
    +Nhập tên đăng nhập là Administrator và mật khẩu tương ứng.

Bước 4: Cài đặt XAMPP trên Windows
  
  -Tải XAMPP: Truy cập vào trang XAMPP và tải xuống phiên bản XAMPP dành cho Windows.
  
  -Cài đặt XAMPP:
    
    +Mở file cài đặt .exe đã tải xuống.
    +Chọn các thành phần cần cài đặt (HTTP Server, MySQL, PHP, Perl).
    +Chọn thư mục cài đặt (mặc định là C:\xampp).
    +Nhấn "Next" và hoàn tất quá trình cài đặt.
  
  -Khởi động XAMPP:
    
    +Mở XAMPP Control Panel từ menu Start.
    +Nhấn nút "Start" bên cạnh Apache và MySQL để khởi động các dịch vụ.

Bước 5: Triển khai ứng dụng PHP

-Chép mã nguồn PHP vào thư mục XAMPP:
  
  +Mặc định, thư mục chứa ứng dụng web là C:\xampp\htdocs\.
  +Bạn có thể sao chép mã nguồn PHP của mình vào thư mục này bằng cách sử dụng Remote Desktop hoặc upload qua FTP.

-Thay đổi quyền truy cập (không cần trên Windows): Trên Windows, bạn không cần thay đổi quyền truy cập như trên Linux.

Bước 6: Cấu hình cơ sở dữ liệu (nếu cần)

-Khởi động phpMyAdmin: Mở trình duyệt và nhập http://ec2-13-239-121-244.ap-southeast-2.compute.amazonaws.com/phpmyadmin.
