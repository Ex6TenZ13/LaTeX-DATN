# LaTeX-DATN

[![LaTeX PDF and release](https://github.com/Ex6TenZ13/LaTeX-DATN/actions/workflows/latex.yml/badge.svg?branch=main)](https://github.com/Ex6TenZ13/LaTeX-DATN/actions/workflows/latex.yml)

> 📣 **Mẫu LaTeX DATN đang trong quá trình chỉnh sửa và hoàn thiện**
>
> Nội dung, cấu trúc và định dạng trong các tệp `.tex` có thể thay đổi; PDF và ảnh xem trước sẽ được cập nhật theo. Nếu đang sử dụng mẫu, hãy kiểm tra [bản phát hành mới nhất](https://github.com/Ex6TenZ13/LaTeX-DATN/releases/latest) trước khi bắt đầu hoặc tiếp tục báo cáo.
>
> Có ý tưởng hoặc phát hiện lỗi? Hãy gửi góp ý tại [Issues](https://github.com/Ex6TenZ13/LaTeX-DATN/issues). Vui lòng nêu tệp hoặc phần liên quan, đề xuất hoặc vấn đề, và ảnh minh họa nếu phù hợp.

Mẫu báo cáo đồ án tốt nghiệp bằng LaTeX.

[![Xem trang đầu của báo cáo](preview.png)](https://github.com/Ex6TenZ13/LaTeX-DATN/blob/main/Quyen_DATN.pdf)

Bấm vào ảnh để mở PDF trong trình xem của GitHub. Các bản phát hành và tệp nguồn được lưu tại [GitHub Releases](https://github.com/Ex6TenZ13/LaTeX-DATN/releases/latest).

ZIP mã nguồn của release không bao gồm `README.md`.

## Tải và sử dụng gói ZIP

1. Tải [gói ZIP mã nguồn của bản phát hành mới nhất](https://github.com/Ex6TenZ13/LaTeX-DATN/releases/latest/download/LaTeX-DATN-source.zip) từ mục **Assets** trong trang Releases.
2. Giải nén ZIP vào một thư mục trên máy tính; không mở hoặc biên dịch tệp `.tex` trực tiếp bên trong ZIP. Giữ nguyên cấu trúc thư mục và các tệp đi kèm.
3. Mở TeXstudio, dùng **File → Open** để đi tới thư mục vừa giải nén và mở `Quyen_DATN.tex`. TeXstudio sẽ hiển thị các tệp cùng thư mục trong **File Explorer**; chọn **Build & View** hoặc nhấn `F5` để biên dịch và xem PDF.

Gói ZIP chứa mã nguồn và tài nguyên của mẫu, không phải file PDF đã biên dịch. Nếu TeXstudio/MiKTeX hỏi cài package còn thiếu, hãy cho phép cài đặt rồi biên dịch lại.

## Cài đặt trên Windows

### 1. MiKTeX

1. Tải **Basic MiKTeX Installer** từ [trang cài đặt chính thức](https://miktex.org/howto/install-miktex).
2. Cài cho người dùng hiện tại, chọn khổ giấy A4 và cho phép tự động cài các gói còn thiếu.
3. Mở **MiKTeX Console**, chọn **Updates** và cài toàn bộ bản cập nhật trước khi biên dịch.

### 2. TeXstudio

1. Tải và cài [TeXstudio](https://texstudio.org/).
2. Mở `Quyen_DATN.tex`.
3. Trong **Options → Configure TeXstudio → Build**, chọn trình biên dịch mặc định là **PdfLaTeX**; nhấn **Build & View** hoặc `F5`.

### 3. SumatraPDF

Tải [SumatraPDF](https://www.sumatrapdfreader.org/download-free-pdf-viewer) để xem PDF và đồng bộ vị trí giữa mã nguồn với tài liệu. Trong TeXstudio, chọn **Options → Configure TeXstudio → Commands → External PDF Viewer** rồi nhập:

```text
"C:/Program Files/SumatraPDF/SumatraPDF.exe" -reuse-instance -forward-search "?c:am.tex" @ "?am.pdf"
```

Để tìm ngược từ PDF về mã nguồn, mở **Settings → Options** của SumatraPDF và đặt lệnh inverse search theo [hướng dẫn tích hợp LaTeX](https://www.sumatrapdfreader.org/docs/LaTeX-integration):

```text
"C:\Program Files\TeXstudio\texstudio.exe" "%f" -line %l
```
