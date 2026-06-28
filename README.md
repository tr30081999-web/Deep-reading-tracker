# 📖 Deep Reading Tracker

Hệ thống theo dõi thói quen đọc sách sâu — track habit, ghi insight, phân tích pattern.

**Live app:** `https://<your-username>.github.io/deep-reading-tracker`

---

## Tính năng

- **Track** — ghi lại mỗi buổi đọc / nghe sách với insight và trạng thái tâm trí
- **Dashboard** — heatmap, bar chart, phân tích tâm trạng → độ sâu
- **Dữ liệu** — export JSON / CSV / báo cáo insight, import để restore
- **PWA** — cài như app trên điện thoại, hoạt động offline

---

## Setup GitHub Pages (5 phút)

### Bước 1 — Tạo repo

```bash
# Tạo repo mới trên github.com tên là: deep-reading-tracker
# Sau đó clone về máy
git clone https://github.com/<your-username>/deep-reading-tracker.git
cd deep-reading-tracker
```

### Bước 2 — Copy files vào repo

Copy toàn bộ nội dung folder này vào repo vừa clone:
```
deep-reading-tracker/
├── index.html
├── manifest.json
├── sw.js
├── README.md
└── assets/
    ├── logo.jpg
    ├── favicon.ico
    ├── favicon-32.png
    ├── favicon-16.png
    ├── apple-touch-icon.png
    └── icon-512.png
```

### Bước 3 — Push lên GitHub

```bash
git add .
git commit -m "Initial deploy"
git push origin main
```

### Bước 4 — Bật GitHub Pages

1. Vào repo trên github.com
2. **Settings** → **Pages**
3. Source: **Deploy from a branch**
4. Branch: **main** / **root**
5. Save

Sau ~1 phút app sẽ live tại:
`https://<your-username>.github.io/deep-reading-tracker`

---

## Workflow backup dữ liệu

```
Dùng app hàng ngày
    ↓
Mỗi tuần / tháng: Tab "Dữ liệu" → Export JSON
    ↓
Lưu file JSON vào Google Drive / iCloud
    ↓
Khi đổi máy / update app: Import JSON → dữ liệu merge tự động
```

## Export để phân tích tháng

1. Tab **Dữ liệu** → **Export báo cáo insight** → chọn "30 ngày"
2. Tải file `.txt`
3. Paste vào Claude và hỏi: *"Phân tích thói quen đọc sách của mình trong tháng này"*

---

## Update app

Khi có phiên bản mới, chỉ cần thay `index.html` và push:

```bash
# Copy index.html mới vào folder
git add index.html
git commit -m "Update app v2"
git push origin main
```

Dữ liệu trong `localStorage` không bị ảnh hưởng khi update code.

> ⚠️ **Lưu ý:** `localStorage` gắn với domain. Nếu đổi sang domain khác, export JSON trước rồi import lại.
