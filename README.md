# Hành trình của kẻ khờ

Bài thuyết trình tiếng Việt về giải tích hàm, được làm bằng
[Quarto](https://quarto.org/) và [Reveal.js](https://revealjs.com/). Nội dung
dẫn từ không gian metric, Banach và Hilbert đến các định lý nền tảng, lý thuyết
phổ, bán nhóm và phương trình tiến hóa.

## Xem trực tuyến

Sau khi GitHub Pages được bật và workflow chạy thành công, bài thuyết trình có
thể xem tại:

<https://khoaltd.github.io/mathematic/>

## Chạy trên máy

Cài [Quarto](https://quarto.org/docs/get-started/) rồi chạy:

```sh
quarto preview
```

Để xuất bản bản tĩnh vào thư mục `_site`:

```sh
quarto render
```

## Cập nhật website sau khi chỉnh sửa

Chỉnh sửa nội dung slide trong `index.qmd` (hoặc giao diện trong `styles.scss`),
rồi mở terminal tại thư mục dự án và chạy **một lần**:

```sh
git add -A && git commit -m "Update presentation" && git push origin main
```

Lệnh này thêm tất cả thay đổi vào commit, lưu commit và đẩy lên GitHub. Khi
`push` thành công, GitHub Actions sẽ tự chạy `quarto render` và cập nhật website
trong vài phút; không cần chạy `quarto render` riêng để xuất bản. Nếu không có
thay đổi mới để commit, hãy chỉnh sửa/lưu ít nhất một file trước khi chạy lệnh.

Lệnh này đưa **mọi thay đổi trong repository** lên GitHub. Trước khi chạy, kiểm
tra `git status` để chắc các thay đổi cần đưa lên đều có thể được chia sẻ.

## Xuất bản lên GitHub Pages

Workflow tại `.github/workflows/publish.yml` tự dựng và xuất bản slide khi có
thay đổi được push lên nhánh `main` (hoặc khi chạy thủ công).

Lần đầu thiết lập, vào **Settings → Pages** của repository và chọn **GitHub
Actions** làm nguồn triển khai. Sau đó, mở tab **Actions** để theo dõi workflow.
