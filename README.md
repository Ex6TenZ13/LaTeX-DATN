# LaTeX-DATN

Mẫu báo cáo đồ án tốt nghiệp bằng LaTeX.

[![Xem trang đầu của báo cáo](preview.png)](https://github.com/Ex6TenZ13/LaTeX-DATN/blob/main/Quyen_DATN.pdf)

Bấm vào ảnh để mở PDF trong trình xem của GitHub. Các bản phát hành và tệp nguồn được lưu tại [GitHub Releases](https://github.com/Ex6TenZ13/LaTeX-DATN/releases/latest).

## Biên dịch

Tài liệu chính là `Quyen_DATN.tex`. Dự án dùng `latexmk` với `pdfLaTeX` và BibTeX:

```powershell
latexmk -pdf -interaction=nonstopmode -file-line-error Quyen_DATN.tex
```

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

## Phát hành tự động

Mỗi lần đẩy tag dạng `v*`, GitHub Actions sẽ biên dịch PDF, tạo ảnh xem trước trang đầu và tạo GitHub Release với đúng hai tệp:

- `Quyen_DATN.pdf`
- `LaTeX-DATN-source.zip` — được tạo trực tiếp từ commit của tag bằng `git archive`.

Không tạo tệp `.rar` giả bằng cách đổi tên ZIP. RAR là định dạng có công cụ tạo chính thức theo giấy phép thương mại; nếu cần RAR thật trên CI, hãy dùng runner tự quản lý đã cài WinRAR/RAR và cung cấp giấy phép hợp lệ. ZIP được dùng ở đây để workflow chạy hợp pháp và tái lập trên GitHub-hosted runner.
