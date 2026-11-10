# Hành trình của kẻ khờ

Bài thuyết trình tiếng Việt về giải tích hàm, làm bằng
[Quarto Reveal.js](https://quarto.org/docs/presentations/revealjs/) và đăng
trên GitHub Pages.

## Luồng xem

1. Trang chủ liệt kê 16 chương và liên kết tới phần tra cứu.
2. Chọn một chương để xem danh sách các section.
3. Mở trình chiếu chương để xem slide lời dẫn dạng trích dẫn, rồi chọn section
   trong mục lục chương để đi thẳng tới nội dung tương ứng.
4. Phụ lục cung cấp bảng tổng kết định lý và chỉ mục thuật ngữ có liên kết
   quay về nội dung.

Các section dài được chia thành những slide nối tiếp để tránh tràn nội dung;
liên kết trong mục lục vẫn mở đúng slide đầu của section.
Một số định nghĩa trọng tâm ở Chương 1 có hình minh họa SVG viết trực tiếp,
không cần chạy mã khi render. Sơ đồ tính liên tục minh họa hai lân cận metric
và ánh xạ giữa chúng.

Mỗi chương là một deck Reveal.js độc lập. Trong khi trình chiếu, nhấn `F` để
bật toàn màn hình, dùng phím mũi tên để chuyển slide, hoặc nhấn `M` để mở menu
điều hướng. Dùng nút bảng viết ở góc dưới hoặc phím `B` để mở Chalkboard;
phím `C` bật lớp ghi chú trực tiếp trên slide. Mỗi slide có liên kết ở footer
để quay về mục lục chương. Thanh điều hướng xanh phía trên cho biết section
hiện tại và có thể bấm để chuyển section; dải tiêu đề và footer xanh lấy cảm
hứng từ giao diện Beamer. Footnote nằm trong dải footer. Slide mở đầu mỗi
chương trình bày lời dẫn trong khung trích dẫn trang trí, căn giữa trên nền
trắng. Định lý có liên kết mở trang chứng minh riêng trong tab mới; phần chứng
minh được lưu ngoài deck trình chiếu.

Deck dùng theme trắng; có thể đổi theme nền trong mục `format.revealjs.theme`
của `_quarto.yml`. Chỉnh header, footer và họa tiết trong `reveal.scss`.

## Xem trực tuyến và chạy trên máy

<https://khoaltd.github.io/mathematic/>

Cài [Quarto](https://quarto.org/docs/get-started/), rồi tại thư mục dự án chạy:

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
- `proof/proof-ch01-continuity.qmd`: trang riêng chứa định lý và chứng minh,
  được mở từ slide bằng tab mới.
- `appendices.qmd`: bảng tổng kết định lý và chỉ mục thuật ngữ.
- `assets/logo-dep.svg`: logo trên slide mở đầu, footer và favicon của website; favicon dùng khung nhìn cắt sát biểu tượng để rõ hơn ở kích thước nhỏ.
- `assets/illustrations/`: các sơ đồ vector SVG được nhúng trực tiếp vào slide.
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

Mã nguồn được lưu trên nhánh `source`; nhánh `main` chỉ chứa website đã render.
Sau khi chỉnh sửa nội dung hoặc giao diện trên nhánh `source`, chạy:

```sh
git add -A && git commit -m "Update presentation" && git push origin source
```

GitHub Actions sẽ render toàn bộ dự án, cập nhật các file website trên `main`,
rồi triển khai lên GitHub Pages. Không chỉnh sửa trực tiếp `main`, vì lần render
kế tiếp sẽ thay nội dung nhánh này bằng website mới. Trước khi chạy, kiểm tra
`git status` để chắc các thay đổi cần đưa lên đều có thể được chia sẻ.

Lần đầu xuất bản, vào **Settings → Pages** của repository và chọn **GitHub
Actions** làm nguồn triển khai. Chỉnh sửa dự án trên máy cần bắt đầu từ nhánh
`source` (`git switch source`). Theo dõi quá trình cập nhật trong tab **Actions**.
