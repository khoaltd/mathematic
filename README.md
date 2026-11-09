# Toán học quanh ta

Bài thuyết trình tiếng Việt được làm bằng [Quarto](https://quarto.org/) và
[Reveal.js](https://revealjs.com/), nói về cách toán học xuất hiện trong những
tình huống quen thuộc.

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

## Xuất bản lên GitHub Pages

Workflow tại `.github/workflows/publish.yml` tự dựng và xuất bản slide khi có
thay đổi được push lên nhánh `main` (hoặc khi chạy thủ công).

Lần đầu thiết lập, vào **Settings → Pages** của repository và chọn **GitHub
Actions** làm nguồn triển khai. Sau đó, mở tab **Actions** để theo dõi workflow.
