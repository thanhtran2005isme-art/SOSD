# 🏋️ Quản lý Trung tâm Thể dục

## 👥 Quy trình làm việc nhóm với Git/GitHub

### 📌 Thành viên nhóm

- Thành viên 1: [Tên]
- Thành viên 2: [Tên]
- Thành viên 3: [Tên]

---

## 🚀 Hướng dẫn chi tiết

### 1️⃣ Thiết lập lần đầu (Chỉ làm 1 lần)

```bash
# Clone repository về máy
git clone https://github.com/username/ten-repository.git

# Di chuyển vào thư mục project
cd ten-repository

# Kiểm tra kết nối
git remote -v
```

### 2️⃣ Quy trình làm việc hàng ngày

#### **Bước 1: Cập nhật code mới nhất**

```bash
# Chuyển về branch main
git checkout main

# Lấy code mới nhất từ GitHub
git pull origin main
```

#### **Bước 2: Tạo branch mới cho công việc của bạn**

```bash
# Tạo và chuyển sang branch mới
git checkout -b ten-branch-cua-ban

# Ví dụ:
# git checkout -b feature/quan-ly-hoi-vien
# git checkout -b feature/thanh-toan
# git checkout -b feature/lich-tap
# git checkout -b fix/loi-dang-nhap
```

#### **Bước 3: Code và commit thường xuyên**

```bash
# Xem những file đã thay đổi
git status

# Thêm file vào staging area
git add .
# Hoặc thêm từng file cụ thể
git add index.html

# Commit với message rõ ràng
git commit -m "Mô tả ngắn gọn những gì bạn làm"

# Ví dụ commit message tốt:
# git commit -m "Thêm form đăng ký hội viên"
# git commit -m "Sửa lỗi hiển thị lịch tập"
# git commit -m "Cập nhật giao diện trang chủ"
```

#### **Bước 4: Đẩy code lên GitHub**

```bash
# Push branch của bạn lên GitHub
git push origin ten-branch-cua-ban

# Ví dụ:
# git push origin feature/quan-ly-hoi-vien
```

#### **Bước 5: Tạo Pull Request trên GitHub**

1. Mở trình duyệt, vào repository trên GitHub
2. Sẽ thấy nút **"Compare & pull request"** màu xanh → Nhấn vào
3. Điền thông tin:
   - **Title**: Tóm tắt ngắn gọn
   - **Description**: Mô tả chi tiết những gì đã làm
4. Chọn **base: main** ← **compare: ten-branch-cua-ban**
5. Nhấn **"Create pull request"**
6. Gửi link Pull Request cho team review

#### **Bước 6: Review và Merge**

- Các thành viên khác sẽ xem code và comment (nếu cần)
- Nếu mọi thứ OK, nhấn **"Merge pull request"**
- Nhấn **"Confirm merge"**
- Nhấn **"Delete branch"** (để giữ repo gọn gàng)

#### **Bước 7: Lặp lại từ Bước 1**

```bash
# Quay về main và cập nhật code mới
git checkout main
git pull origin main

# Tạo branch mới cho tính năng tiếp theo
git checkout -b feature/tinh-nang-moi
```

---

## 📋 Quy tắc làm việc nhóm

### ✅ NÊN LÀM:

- ✅ Luôn `git pull` trước khi bắt đầu làm việc mới
- ✅ Tạo branch mới cho mỗi tính năng/công việc
- ✅ Commit thường xuyên với message có ý nghĩa
- ✅ Push code lên GitHub ít nhất 1 lần/ngày
- ✅ Review code của người khác trước khi merge
- ✅ Thông báo team khi merge vào main
- ✅ Đặt tên branch và commit có ý nghĩa

### ❌ KHÔNG NÊN LÀM:

- ❌ Không làm việc trực tiếp trên branch `main`
- ❌ Không commit code chưa test
- ❌ Không push file không liên quan (node_modules, .env, ...)
- ❌ Không merge pull request của mình mà không có người review
- ❌ Không commit message kiểu "update", "fix", "abc"

---

## 🎯 Quy ước đặt tên

### Branch naming:

```
feature/ten-tinh-nang    → Tính năng mới
fix/ten-loi              → Sửa lỗi
update/ten-cap-nhat      → Cập nhật
refactor/ten-module      → Tái cấu trúc code

Ví dụ:
feature/dang-ky-hoi-vien
feature/quan-ly-goi-tap
fix/loi-thanh-toan
update/giao-dien-trang-chu
```

### Commit message:

```
Thêm [tính năng]         → Thêm form đăng ký
Sửa [lỗi]                → Sửa lỗi hiển thị ngày tháng
Cập nhật [nội dung]      → Cập nhật màu sắc button
Xóa [nội dung]           → Xóa code không dùng
Refactor [module]        → Refactor module thanh toán
```

---

## 🆘 Xử lý tình huống thường gặp

### 1. Conflict khi merge

```bash
# Cập nhật code từ main
git checkout main
git pull origin main

# Quay về branch của bạn
git checkout ten-branch-cua-ban

# Merge main vào branch của bạn
git merge main

# Nếu có conflict, mở file và sửa phần conflict
# Tìm các dòng có <<<<<<< HEAD, =======, >>>>>>>

# Sau khi sửa xong
git add .
git commit -m "Giải quyết conflict với main"
git push origin ten-branch-cua-ban
```

### 2. Quên pull trước khi làm việc

```bash
# Stash (tạm cất) code đang làm
git stash

# Pull code mới
git pull origin main

# Lấy lại code đã stash
git stash pop
```

### 3. Commit nhầm file

```bash
# Hủy commit gần nhất (giữ lại code)
git reset --soft HEAD~1

# Hoặc hủy commit và xóa luôn thay đổi (NGUY HIỂM!)
git reset --hard HEAD~1
```

### 4. Muốn xem ai làm gì

```bash
# Xem lịch sử commit
git log

# Xem lịch sử chi tiết của 1 file
git log -p index.html

# Xem ai sửa dòng nào
git blame index.html
```

---

## 📚 Câu lệnh Git thường dùng

```bash
# Kiểm tra trạng thái
git status                           # Xem file nào đã thay đổi
git branch                           # Xem danh sách branch
git branch -a                        # Xem tất cả branch (cả remote)

# Di chuyển giữa các branch
git checkout ten-branch              # Chuyển sang branch khác
git checkout -b branch-moi           # Tạo và chuyển sang branch mới
git checkout main                    # Quay về main

# Làm việc với code
git add .                            # Thêm tất cả file đã thay đổi
git add ten-file.html                # Thêm file cụ thể
git commit -m "Message"              # Commit với message
git push origin ten-branch           # Đẩy code lên GitHub
git pull origin main                 # Lấy code về từ GitHub

# Xem thông tin
git log                              # Xem lịch sử commit
git log --oneline                    # Xem lịch sử ngắn gọn
git diff                             # Xem những thay đổi chưa commit
git remote -v                        # Xem thông tin remote repository

# Xóa branch
git branch -d ten-branch             # Xóa branch local (đã merge)
git branch -D ten-branch             # Xóa branch local (force)
git push origin --delete ten-branch  # Xóa branch trên GitHub
```

---

## 🎓 Workflow tóm tắt

```
1. git checkout main
2. git pull origin main
3. git checkout -b feature/ten-tinh-nang
4. [Code xong]
5. git add .
6. git commit -m "Mô tả công việc"
7. git push origin feature/ten-tinh-nang
8. [Tạo Pull Request trên GitHub]
9. [Review và Merge]
10. Lặp lại từ bước 1
```

---

## 📞 Liên hệ và hỗ trợ

Nếu gặp vấn đề:

1. Google: "git [vấn đề của bạn]"
2. Hỏi team trong nhóm
3. Xem tài liệu: https://git-scm.com/doc

---

## 📝 Ghi chú

- Link repository: https://github.com/thanhtran2005isme-art/SOSD
- Người quản lý chính: Admin
- Ngày bắt đầu dự án: 21/11/2025

---

**Chúc team làm việc hiệu quả! 🎉**
