# Linux
## Kiến thức cần nắm:
- [Các lệnh cơ bản thường dùng](#các-lệnh-cơ-bản-thường-dùng)

- Cấu trúc thư mục (/etc, /var, /home, /usr, /tmp)

- Quản lý user và phân quyền

- Câu lệnh xử lý hệ thống

- Kiểm tra tiến trình, log hệ thống

- Quản lý file (phân quyền, thuộc tính)

## Câu hỏi kiểm tra:

- Thư mục /etc/passwd và /etc/shadow chứa thông tin gì? Phân biệt ra sao?

- Câu lệnh nào để xem danh sách các tiến trình đang chạy?

- Làm sao để xem log đăng nhập của user trong Linux?

- Nếu file có quyền -rw-r--r--, thì user nào có thể sửa file?

- Câu lệnh để liệt kê các port đang lắng nghe trên hệ thống?

- Câu lệnh nào để kiểm tra lịch sử đăng nhập gần đây?

- Bạn có thể dùng lệnh nào để xem dung lượng ổ đĩa đang sử dụng?

## Các lệnh cơ bản thường dùng
- **ls: Dùng để liệt kê các file và thư mục trong một thư mục nào đó**
  - Cú pháp cơ bản : ls [tùy chọn] [đường_dẫn]
  - ls	Liệt kê các file/thư mục trong thư mục hiện tại
  - ls -l	Liệt kê chi tiết (dạng danh sách, có quyền, chủ sở hữu, dung lượng...)
  - ls -a	Hiện cả file ẩn (bắt đầu bằng dấu .)
  - ls -lh	Hiển thị dung lượng dễ đọc hơn (K, M, G)
  - ls -R	Liệt kê đệ quy (cả thư mục con)
  - ls /home/user/	Liệt kê file/thư mục trong /home/user/

- **cd : Lệnh cd trong Linux được sử dụng để thay đổi thư mục làm việc hiện tại. Đây là lệnh rất cơ bản và quan trọng trong việc điều hướng hệ thống file.**
  - cd / : Lệnh này đưa bạn về thư mục gốc của hệ thống (/).
  - cd - : Nếu bạn đã chuyển đến một thư mục khác và muốn quay lại thư mục trước đó, lệnh này sẽ giúp bạn làm điều đó.
  - cd ~ : Dấu ~ đại diện cho thư mục home của người dùng hiện tại. Ví dụ: nếu người dùng là user, lệnh này sẽ đưa bạn đến thư mục /home/user.
  - cd .. : Lệnh này đưa bạn lùi một cấp trong cây thư mục (ví dụ: từ /home/user/documents về /home/user).

- **mkdir : Lệnh mkdir trong Linux được sử dụng để tạo một thư mục mới.**
  - mkdir new_folder : Tạo thư mục mới tại thư mục hiện tại
  - mkdir /home/user/new_folder :  tạo thư mục new_folder trong thư mục /home/user/
  - mkdir folder1 folder2 folder3 : Tạo nhiều thư mục cùng lúc
  - mkdir -m 755 new_folder : Lệnh này tạo thư mục new_folder và thiết lập quyền truy cập mặc định là 755 (người sở hữu có quyền đọc, ghi, thực thi; nhóm và người khác có quyền đọc, thực thi).
  - -p	Tạo các thư mục cha nếu chúng chưa tồn tại
  - -m	Chỉ định quyền truy cập cho thư mục mới
  - -v	Hiển thị thông báo khi thư mục được tạo
  
- **pwd : Lệnh pwd trong Linux là viết tắt của Print Working Directory, và nó được sử dụng để hiển thị đường dẫn đầy đủ của thư mục hiện tại mà bạn đang làm việc.**

- **mv : Lệnh mv trong Linux được sử dụng để di chuyển hoặc đổi tên các file và thư mục.**
  - mv file.txt /home/user/documents/ : Lệnh này sẽ di chuyển file file.txt từ thư mục hiện tại sang thư mục /home/user/documents/
  - mv old_file.txt new_file.txt : Lệnh này sẽ đổi tên file old_file.txt thành new_file.txt trong cùng thư mục.
  - mv folder1 /home/user/documents/ : Lệnh này sẽ di chuyển thư mục folder1 vào thư mục /home/user/documents/.
  - mv file.txt /home/user/documents/new_file.txt : Lệnh này sẽ di chuyển file file.txt từ thư mục hiện tại vào thư mục /home/user/documents/ và đổi tên nó thành new_file.txt
  
- **rm : Lệnh rm trong Linux được sử dụng để xóa file hoặc thư mục.**
  - rm file.txt : Xoá 1 file
  - rm file1.txt file2.txt : Xoá nhiều file
  - rm -r folder_name : Tùy chọn -r (recursive) cho phép xóa thư mục và tất cả các thư mục con và file bên trong nó
  - rm -f file.txt : Tùy chọn -f (force) giúp xóa file mà không yêu cầu xác nhận (ngay cả khi file bị chỉ đọc hoặc không có quyền).
  - rmdir folder_name : Xoá thư mục rỗng
  - rm -rf folder_name: Kết hợp -rf để xóa thư mục và tất cả nội dung bên trong mà không yêu cầu xác nhận
  - -r	Recursive: Xóa thư mục và tất cả nội dung bên trong.
  - -f	Force: Xóa mà không yêu cầu xác nhận, kể cả khi file có quyền chỉ đọc.
  - -i	Interactive: Hỏi xác nhận trước khi xóa mỗi file.
  - -v	Verbose: Hiển thị thông báo khi xóa mỗi file.

- **cp:  Lệnh cp trong Linux dùng để sao chép file hoặc thư mục từ nơi này sang nơi khác.**
  - cp file.txt /home/user/ : Sao chép file.txt vào thư mục /home/user/
  - cp file.txt newfile.txt : Tạo bản sao của file.txt với tên mới là newfile.txt
  - cp -r my_folder /home/user/ : Sao chép toàn bộ thư mục my_folder và nội dung bên trong.
  - -r	Sao chép thư mục và các file con bên trong (recursive).
  - -i	Hỏi trước khi ghi đè file.
  - -f	Ghi đè không cần hỏi.
  - -v	Hiển thị quá trình sao chép (verbose).
  - -u	Chỉ sao chép nếu file nguồn mới hơn hoặc file đích chưa tồn tại.

- **find: Lệnh find trong Linux dùng để tìm kiếm file hoặc thư mục theo tên, loại, ngày sửa đổi, quyền, kích thước,... trong một thư mục và các thư mục con.**
  - -name	Tìm theo tên chính xác (phân biệt hoa thường)
  - -iname	Tìm theo tên không phân biệt hoa thường
  - -type f	Tìm file
  - -type d	Tìm thư mục
  - -size	Tìm theo kích thước
  - -mtime	Tìm theo thời gian sửa đổi
  - -delete	Xóa luôn file tìm được (cẩn thận!)
- **chmod: Lệnh chmod trong Linux dùng để thay đổi quyền truy cập (read, write, execute) của file hoặc thư mục**
    - Cách dùng gắn quyền kiểu số: chmod 755 filename ( user:rwx , group:rx , other:rx )
    - Cách gắn dùng kiểu ký tự: chmod u+x filename
    - u	user (chủ sở hữu), g	group (nhóm), o	others (người khác), a	all (tất cả), +	thêm quyền, -	xóa quyền, =	gán đúng quyền, xóa phần còn lại
    - VD: chmod ug+rwx hello
- **cat: đọc file**
  - Ví dụ minh họa:
  - cat ./flag.txt → đọc file trong thư mục hiện tại.
  - cat ../flag.txt → đọc file ở thư mục cha.
  - cat /home/user/flag.txt → đọc file ở đường dẫn tuyệt đối.
  - cat /flag.txt → đọc file nằm ở thư mục gốc hệ thống.

- 
- hj
- `ls`, `cd`, `pwd`, `mkdir`, `rm`, `cp`, `mv`, ...
- `cat`, `less`, `more`, `head`, `tail`
- `chmod`, `chown`, `ps`, `kill`, ...
