# Hành trình của kẻ khờ

Bài thuyết trình tiếng Việt về giải tích hàm, làm bằng
[Quarto Reveal.js](https://quarto.org/docs/presentations/revealjs/) và đăng
trên GitHub Pages.

## Luồng xem

1. Trang chủ liệt kê 16 chương và liên kết tới phần tra cứu.
2. Chọn một chương để xem danh sách các section.
3. Chọn một section để mở bài trình chiếu riêng của chương tại đúng slide đó.
4. Phụ lục cung cấp bảng tổng kết định lý và chỉ mục thuật ngữ có liên kết
   quay về nội dung.

Mỗi chương là một deck Reveal.js độc lập. Trong khi trình chiếu, nhấn `F` để
bật toàn màn hình, dùng phím mũi tên để chuyển slide, hoặc nhấn `M` để mở menu
điều hướng. Dùng nút bảng viết ở góc dưới hoặc phím `B` để mở Chalkboard;
phím `C` bật lớp ghi chú trực tiếp trên slide. Mỗi slide có liên kết ở footer
để quay về mục lục chương.

Deck dùng theme trắng; có thể đổi theme nền trong mục `format.revealjs.theme`
của `_quarto.yml`. Chỉnh header, footer và họa tiết trong `reveal.scss`.

## Xem trực tuyến và chạy trên máy

<https://khoaltd.github.io/mathematic/>

Cài [Quarto](https://quarto.org/docs/get-started/), rồi tại thư mục dự án
chạy:

```sh
quarto preview
```

Để dựng toàn bộ website vào `_site`:

```sh
quarto render
```

## Cấu trúc nội dung

- `index.qmd`: trang chủ chỉ liệt kê các chương.
- `foreword.qmd`: lời nói đầu từ bản thảo.
- `chapters/ch01.qmd` … `chapters/ch16.qmd`: trang mục lục section của từng
  chương.
- `slides/ch01.qmd` … `slides/ch16.qmd`: bài trình chiếu Reveal.js riêng cho
  từng chương.
- `appendices.qmd`: bảng tổng kết định lý và chỉ mục thuật ngữ.
- `_quarto.yml`: cấu hình website và Reveal.js.
- `reveal.scss`: giao diện slide và các khối định nghĩa/định lý.
- `styles.scss`: giao diện các trang HTML.

Định nghĩa và định lý dùng cú pháp khối Quarto có nhãn riêng để được đánh số
tự động trong bài trình chiếu của chương:

````markdown
::: {#def-metric .def- name="Không gian metric"}
Một định nghĩa có số thứ tự tự động.
:::

::: {#thm-example .thm- name="Định lý mẫu"}
Một định lý có số thứ tự tự động.
:::
````

## Cập nhật website

Sau khi chỉnh sửa nội dung hoặc giao diện, chạy:

```sh
git add -A && git commit -m "Update presentation" && git push origin main
```

Lệnh này thêm mọi thay đổi trong repository vào commit và đẩy lên GitHub. Khi
push thành công, GitHub Actions sẽ tự render và cập nhật website. Trước khi
chạy, kiểm tra `git status` để chắc các thay đổi cần đưa lên đều có thể được
chia sẻ.

Lần đầu xuất bản, vào **Settings → Pages** của repository và chọn **GitHub
Actions** làm nguồn triển khai. Theo dõi quá trình cập nhật trong tab
**Actions**.
