# Lộ trình dữ liệu sạch

## Giai đoạn 0 — nền tảng quyền

- Chốt data policy và schema provenance.
- Tạo registry nguồn và pipeline kiểm tra license.
- Tách code, data gốc, data GPL và data chỉ dùng nội bộ.
- Gửi các yêu cầu cấp phép ưu tiên.

## Giai đoạn 1 — MVP không phụ thuộc quyền chưa rõ

- Unicode/Unihan làm canonical character registry.
- NomNaTong làm font hiển thị.
- Tự biên soạn 500–1.000 mục chữ/từ phổ biến đầu tiên.
- Tự viết ví dụ tiếng Việt hiện đại.
- Dùng văn bản cổ có căn cứ public-domain và tự phiên âm một tập nhỏ.
- Dạy nhận mặt, bộ phận, âm đọc, dị thể và ngữ cảnh.

## Giai đoạn 2 — chuẩn hóa cộng đồng

- Công bố policy chọn chữ chuẩn và cách biểu diễn từ hiện đại.
- Mời chuyên gia Hán Nôm review từng batch.
- Mỗi quyết định có nguồn, phản biện và lịch sử thay đổi.
- Đo coverage trên corpus có quyền sạch, không chỉ dựa vào tuyên bố lý thuyết.

## Giai đoạn 3 — corpus và OCR

- Chỉ nhập scan khi có license/permission rõ.
- Tách image license, transcription license và annotation license.
- Công bố benchmark trên phần dữ liệu được phép redistribution.
- Giữ dataset research-only ở kho riêng, không trộn với open release.

## Điều kiện để tuyên bố “đọc được phần lớn văn bản”

Cần công bố tối thiểu:

- corpus đánh giá gồm những văn bản nào;
- quyền sử dụng corpus;
- tokenization và cách tính coverage;
- coverage theo token và theo type;
- coverage riêng cho văn bản cổ và tiếng Việt hiện đại;
- cách xử lý dị thể, chữ chưa mã hóa và chữ mượn Hán;
- sai số giữa nhận mặt chữ và thực sự đọc hiểu.

