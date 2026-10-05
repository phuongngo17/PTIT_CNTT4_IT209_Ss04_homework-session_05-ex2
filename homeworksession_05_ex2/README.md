\# Bài 2: Tái cấu trúc lịch sử commit bằng Interactive Rebase



> \*\*Lưu ý:\*\* Các ảnh minh chứng của bài được lưu trong thư mục `anh/` của project.



\## 1. Tạo các commit



Khởi tạo Git repository:



```bash

git init

```



Tạo file `auth.js` và tạo commit đầu tiên:



```bash

git add auth.js

git commit -m "feat: khoi tao module auth"

```



Sửa `auth.js` và tạo commit thứ hai:



```bash

git add auth.js

git commit -m "fix typo"

```



Thêm utility function và tạo commit thứ ba:



```bash

git add auth.js

git commit -m "adds utility functions"

```



Tạo file `temp.txt` và tạo commit thứ tư:



```bash

git add temp.txt

git commit -m "add temp file for debug"

```



\## 2. Kiểm tra lịch sử trước khi Rebase



```bash

git log --oneline

```



Lịch sử trước khi Rebase:



```text

1abea0c adds utility functions

4662151 add temp file for debug

1feaeab fix typo

e031371 feat: khoi tao module auth

```



\## 3. Thực hiện Interactive Rebase



```bash

git rebase -i --root

```



Cấu hình Interactive Rebase:



```text

pick e031371 feat: khoi tao module auth

squash 1feaeab fix typo

drop 4662151 add temp file for debug

squash 1abea0c adds utility functions

```



\### Ảnh minh chứng Interactive Rebase



Ảnh được lưu trong thư mục `anh/`:



```text

anh/rebase.png

```



!\[Interactive Rebase](anh/rebase.png)



\## 4. Đổi thông điệp commit sau khi Squash



Sau khi Squash, commit message được thay đổi thành:



```text

feat: hoan thien module authentication

```



Rebase hoàn tất thành công:



```text

Successfully rebased and updated refs/heads/master.

```



\## 5. Kiểm tra lịch sử sau khi Rebase



Chạy:



```bash

git log --oneline

```



Kết quả:



```text

65c6268 (HEAD -> master) feat: hoan thien module authentication

```



\### Ảnh minh chứng log sau khi Rebase



Ảnh được lưu trong thư mục `anh/`:



```text

anh/git-log.png

```



!\[Git log sau Rebase](anh/git-log.png)



\## 6. Kiểm tra file sau khi Rebase



Chạy:



```bash

dir

```



Kết quả chỉ còn:



```text

auth.js

```



File `temp.txt` đã được loại bỏ.



\### Ảnh minh chứng kiểm tra file



Ảnh được lưu trong thư mục `anh/`:



```text

anh/check-files.png

```



!\[Kiểm tra file sau Rebase](anh/check-files.png)





