# BÀI THỰC HÀNH GITHUB – FORK APP, BRANCH VÀ PULL REQUEST

## 1. Mục tiêu

Sau bài thực hành, mỗi thành viên cần biết:

- Clone Repository bằng **Fork App**.
- Phân biệt các branch `main`, `develop` và `feature/*`.
- Hiểu công dụng cơ bản của file `.gitignore`.
- Checkout branch `develop`.
- Tạo branch cá nhân từ `develop`.
- Kiểm tra file thay đổi bằng Fork App.
- Stage file.
- Commit thay đổi.
- Push branch lên GitHub.
- Tạo Pull Request vào `develop`.
- Hiểu quy trình Review và Merge.
- Không code hoặc Push trực tiếp lên `main` và `develop`.

---

## 2. Cấu trúc Branch

Repository chung của nhóm có:

```text
main
develop
```

Trong đó:

- `main`: nhánh chứa phiên bản ổn định.
- `develop`: nhánh tích hợp code của cả nhóm.
- `feature/hovaten`: nhánh làm việc riêng của từng thành viên.

Mỗi thành viên phải tự tạo branch cá nhân từ `develop`.

Ví dụ:

```text
feature/duongkny
```

### Lưu ý

> ❌ Không tạo branch cá nhân từ `main`.  
> ❌ Không code trực tiếp trên `main`.  
> ❌ Không code trực tiếp trên `develop`.

---

## 3. File `.gitignore`

Repository đã được trưởng nhóm chuẩn bị sẵn file:

```text
.gitignore
```

File `.gitignore` được sử dụng để khai báo những file hoặc thư mục mà Git **không cần theo dõi**.

Trong bài thực hành này, `.gitignore` có nội dung:

```gitignore
*.log
*.tmp
```

### Ý nghĩa

```text
*.log
```

→ Git bỏ qua tất cả các file có đuôi `.log`.

```text
*.tmp
```

→ Git bỏ qua tất cả các file có đuôi `.tmp`.

Ví dụ:

```text
test.log
debug.log
data.tmp
```

Các file trên sẽ được Git bỏ qua.

### Lưu ý

- Không chỉnh sửa file `.gitignore`.
- Không xóa file `.gitignore`.
- File `.gitignore` đã được Leader chuẩn bị sẵn.
- Không đưa `test.log` lên GitHub.

---

## 4. Yêu cầu bài tập

Mỗi thành viên thực hiện **2 yêu cầu**.

### Yêu cầu 1 – Tạo file thông tin cá nhân

Mỗi thành viên tạo **01 file `.txt`** mang tên của mình.

Quy tắc đặt tên:

```text
hovaten.txt
```

Ví dụ:

```text
nguyenvana.txt
tranthib.txt
leminhc.txt
```

Nội dung file:

```text
Họ và tên: Nguyễn Văn A

Vai trò: Frontend Developer

Giới thiệu:
Tôi đang thực hành Git/GitHub bằng Fork App.

Branch:
feature/nguyenvana
```

### Yêu cầu 2 – Kiểm tra `.gitignore`

Mỗi thành viên tạo thêm file:

```text
test.log
```

Có thể nhập nội dung:

```text
This is a test log file.
```

Do `.gitignore` có:

```gitignore
*.log
```

nên `test.log` phải được Git bỏ qua.

Kết quả mong muốn:

| File | Git theo dõi | Commit | Push |
|---|:---:|:---:|:---:|
| `hovaten.txt` | ✅ | ✅ | ✅ |
| `test.log` | ❌ | ❌ | ❌ |

---

# 5. Quy trình thực hiện

## Bước 1 – Clone Repository

Trưởng nhóm sẽ cung cấp đường dẫn GitHub Repository.

Mở **Fork App**:

```text
File
  ↓
Clone...
```

Dán đường dẫn Repository được cung cấp và Clone project về máy.

---

## Bước 2 – Checkout `develop`

Sau khi Clone thành công, tìm các branch:

```text
main
develop
```

Chuyển sang:

```text
develop
```

Trước khi bắt đầu bài tập, phải kiểm tra chắc chắn mình đang đứng ở branch `develop`.

---

## Bước 3 – Tạo Branch cá nhân

Từ `develop`, mỗi thành viên tự tạo branch theo cấu trúc:

```text
feature/hovaten
```

Ví dụ:

```text
feature/nguyenvana
```

Sau khi tạo branch phải Checkout sang branch vừa tạo.

```text
develop
   │
   └── feature/nguyenvana
               ↑
          LÀM BÀI TẠI ĐÂY
```

Kiểm tra branch hiện tại trước khi tiếp tục.

---

## Bước 4 – Tạo file `.txt`

Trong thư mục project, tạo:

```text
hovaten.txt
```

Ví dụ:

```text
nguyenvana.txt
```

Nội dung:

```text
Họ và tên: Nguyễn Văn A

Vai trò: Frontend Developer

Giới thiệu:
Tôi đang thực hành Git/GitHub bằng Fork App.

Branch:
feature/nguyenvana
```

Sau đó lưu file.

---

## Bước 5 – Tạo file `test.log`

Trong cùng thư mục project, tạo thêm:

```text
test.log
```

Ví dụ nội dung:

```text
This is a test log file.
```

Lúc này trên máy có thể có:

```text
Repository/
│
├── README.md
├── .gitignore
├── nguyenvana.txt
└── test.log
```

Trong đó:

- `nguyenvana.txt` → Git phải theo dõi.
- `test.log` → Git phải bỏ qua.

---

## Bước 6 – Kiểm tra thay đổi

Quay lại **Fork App**.

Vào:

```text
Local Changes
```

File `.txt` vừa tạo phải xuất hiện trong:

```text
Unstaged
└── nguyenvana.txt
```

Trong khi đó:

```text
test.log
```

**không được xuất hiện trong Local Changes thông thường** vì đã bị `.gitignore` bỏ qua.

Nếu `test.log` không xuất hiện thì `.gitignore` đang hoạt động đúng.

---

## Bước 7 – Stage File

Chọn file `.txt` vừa tạo và thực hiện **Stage**.

```text
Unstaged
    ↓
  Stage
    ↓
 Staged
```

Kết quả:

```text
Staged
└── nguyenvana.txt
```

Chỉ Stage file:

```text
hovaten.txt
```

Không Stage:

```text
test.log
```

---

## Bước 8 – Commit

Nhập Commit Subject theo cấu trúc:

```text
feat: add Ho Ten profile
```

Ví dụ:

```text
feat: add Nguyen Van A profile
```

Sau đó thực hiện **Commit**.

### Không sử dụng Commit Message như:

```text
update
code
abc
123
done
```

Commit Message cần ngắn gọn và mô tả được thay đổi đã thực hiện.

---

## Bước 9 – Push Branch lên GitHub

Sau khi Commit thành công, sử dụng chức năng:

```text
Push
```

Phải Push branch cá nhân:

```text
feature/hovaten
```

Ví dụ:

```text
feature/nguyenvana
```

Quy trình:

```text
Local

feature/nguyenvana
        │
        │ Push
        ↓
GitHub

origin/feature/nguyenvana
```

### Không Push trực tiếp lên:

```text
main     ❌
develop  ❌
```

---

## Bước 10 – Tạo Pull Request

Sau khi Push thành công, truy cập Repository trên GitHub.

Tạo **Pull Request** với:

```text
base: develop
compare: feature/hovaten
```

Ví dụ:

```text
base: develop
compare: feature/nguyenvana
```

Có nghĩa là:

```text
feature/nguyenvana
        │
        │ Pull Request
        ↓
     develop
```

> ❌ **Không tạo Pull Request vào `main`.**

---

## Bước 11 – Nội dung Pull Request

### Tiêu đề

```text
[Feature] Add Ho Ten profile
```

Ví dụ:

```text
[Feature] Add Nguyen Van A profile
```

### Description

```markdown
## Nội dung

- Thêm file giới thiệu cá nhân.
- Thêm họ tên.
- Thêm vai trò.
- Thêm câu giới thiệu.
- Đã kiểm tra hoạt động của .gitignore.

## Branch

feature/nguyenvana
```

Sau đó chọn:

```text
Create Pull Request
```

---

## Bước 12 – Chờ Review

Sau khi tạo Pull Request:

> ⛔ **KHÔNG ĐƯỢC TỰ MERGE.**

Trưởng nhóm sẽ kiểm tra Pull Request.

Quy trình:

```text
feature/hovaten
        ↓
   Pull Request
        ↓
   Leader Review
```

Leader sẽ kiểm tra:

- Branch có đúng không.
- File `.txt` có đúng yêu cầu không.
- Commit Message có đúng không.
- `test.log` có bị đưa lên GitHub không.
- Pull Request có đúng vào `develop` không.

---

## Bước 13 – Sửa bài nếu được yêu cầu

Nếu Leader yêu cầu chỉnh sửa, thành viên phải quay lại chính branch:

```text
feature/hovaten
```

> ❌ Không tạo branch mới.  
> ❌ Không tạo Pull Request mới.

Thực hiện:

```text
Sửa file
   ↓
Save
   ↓
Stage
   ↓
Commit
   ↓
Push
```

Ví dụ Commit lần 2:

```text
fix: update profile information
```

Sau khi Push, **Pull Request cũ sẽ tự động cập nhật Commit mới**.

---

## Bước 14 – Merge

Khi bài làm đạt yêu cầu, **Leader** sẽ Merge Pull Request.

```text
feature/hovaten
        ↓
   Pull Request
        ↓
     Review
        ↓
      Merge
        ↓
     develop
```

> Thành viên **không tự Merge**.

---

# 6. Quy định

## ❌ Không được

- Code trực tiếp trên `main`.
- Code trực tiếp trên `develop`.
- Push trực tiếp lên `main`.
- Push trực tiếp lên `develop`.
- Tạo branch cá nhân từ `main`.
- Tạo Pull Request vào `main`.
- Tự Merge Pull Request.
- Xóa hoặc chỉnh sửa `.gitignore` trong bài thực hành này.
- Đưa `test.log` lên GitHub.

## ✅ Được phép

- Clone Repository.
- Checkout `develop`.
- Tạo branch từ `develop`.
- Làm bài trên `feature/hovaten`.
- Commit trên `feature/hovaten`.
- Push `feature/hovaten`.
- Tạo Pull Request từ `feature/hovaten` vào `develop`.
- Tiếp tục sửa trên branch cũ nếu Leader yêu cầu chỉnh sửa.

---

# 7. Kết quả mong muốn

Trên máy của mỗi thành viên có thể có:

```text
Repository/
│
├── README.md
├── .gitignore
├── hovaten.txt
└── test.log
```

Trong đó:

```text
README.md
→ Có sẵn trong Repository.

.gitignore
→ Có sẵn trong Repository.

hovaten.txt
→ Được Git theo dõi.

test.log
→ Bị .gitignore bỏ qua.
```

Sau khi tất cả thành viên hoàn thành và các Pull Request được Leader Merge:

```text
develop
│
├── README.md
├── .gitignore
├── duong.txt
├── thuc.txt
├── trang.txt
└── chi.txt
```

Repository trên GitHub **không được có**:

```text
test.log
```

Mỗi file của thành viên phải được đưa vào `develop` thông qua **Pull Request**.

---

# 8. Quy trình cần nhớ

```text
CLONE REPOSITORY
        ↓
CHECKOUT DEVELOP
        ↓
TẠO FEATURE/HOVATEN
        ↓
TẠO HOVATEN.TXT
        ↓
TẠO TEST.LOG
        ↓
KIỂM TRA .GITIGNORE
        ↓
LOCAL CHANGES
        ↓
STAGE HOVATEN.TXT
        ↓
COMMIT
        ↓
PUSH FEATURE/HOVATEN
        ↓
PULL REQUEST
        ↓
FEATURE/HOVATEN → DEVELOP
        ↓
LEADER REVIEW
        ↓
MERGE
        ↓
DEVELOP
```

---

# ⚠️ Yêu cầu quan trọng nhất

### `main`

```text
KHÔNG CODE TRỰC TIẾP
KHÔNG PUSH TRỰC TIẾP
```

### `develop`

```text
KHÔNG CODE TRỰC TIẾP
KHÔNG PUSH TRỰC TIẾP
```

### `feature/hovaten`

```text
NƠI THÀNH VIÊN LÀM BÀI
        ↓
STAGE
        ↓
COMMIT
        ↓
PUSH
```

### `hovaten.txt`

```text
ĐƯỢC GIT THEO DÕI
ĐƯỢC COMMIT
ĐƯỢC PUSH
```

### `test.log`

```text
BỊ .GITIGNORE BỎ QUA
KHÔNG COMMIT
KHÔNG PUSH
```

### Pull Request

```text
feature/hovaten
        ↓
     develop
```

### Merge

```text
LEADER REVIEW
      ↓
    MERGE
      ↓
   develop
```

---

## Tóm tắt

> **Thành viên chỉ làm việc trên `feature/hovaten`.**
>
> **Mọi thay đổi muốn vào `develop` đều phải thông qua Pull Request.**
>
> **Không Push trực tiếp vào `main` hoặc `develop`.**