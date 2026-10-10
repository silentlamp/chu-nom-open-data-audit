# Mô hình quyền và provenance

## Một mục chữ không phải một quyền duy nhất

Ví dụ một trang học chữ có thể chứa đồng thời:

| Lớp | Ví dụ | Cách xử lý |
|---|---|---|
| Ký tự | `𠊛`, U+2029B | Lấy mã và thuộc tính từ Unicode |
| Hình glyph | đường nét trong font | Tuân license font, không cắt từ code chart |
| Âm đọc | `người` | Lưu nguồn và mức đồng thuận |
| Nghĩa/định nghĩa | văn bản giải nghĩa | Tự biên soạn hoặc xin phép từ điển |
| IDS | cấu trúc `⿰...` | Tuân GPL/nguồn IDS |
| Dị thể | quan hệ giữa hai code point | Lưu nguồn riêng cho từng cạnh |
| Ví dụ | câu trích tác phẩm | Audit tác phẩm và edition |
| Scan | ảnh trang sách | Xin kho lưu trữ/chủ bản số |
| Phiên âm | Nôm → Quốc ngữ | Có thể là tác phẩm mới |
| Chú giải | giải thích ngữ pháp/văn hóa | Tự viết hoặc xin phép |
| Tần suất | thống kê từ corpus | Audit corpus và mô tả phương pháp |

## Schema provenance tối thiểu

Mỗi record dữ liệu nên có:

```yaml
id: stable-project-id
value: "..."
source_id: unicode-unihan
source_locator: "file/record/page"
retrieved_at: 2026-10-10
license_spdx: Unicode-3.0
license_evidence_url: "https://unicode.org/policies/licensing_policy.html"
rights_holder: Unicode, Inc.
redistribution_status: allowed
modification_status: allowed
commercial_status: allowed
attribution: required
reviewed_by: "..."
reviewed_at: 2026-10-10
notes: "..."
```

## Quy tắc nhập dữ liệu

1. Không có license không có nghĩa public domain.
2. Publicly accessible không có nghĩa được redistribute.
3. License của code không tự động áp dụng cho dataset đi kèm.
4. License của annotation không xóa quyền ở ảnh hoặc text upstream.
5. Một tác phẩm cổ hết hạn không làm bản scan/chú giải mới hết quyền.
6. Không gộp các nguồn có license xung đột thành một file không thể tách.
7. Lưu snapshot bằng chứng license hoặc hash và URL; điều khoản web có thể thay đổi.
8. Mọi permission riêng phải được lưu cùng phạm vi, ngày và người cấp phép.

## Tiêu chí “green” của dự án

Một nguồn chỉ được đánh dấu xanh cho redistribution khi có bằng chứng cho phép:

- reproduce;
- modify/adapt;
- redistribute;
- public display/API/offline package;
- commercial downstream use;
- sublicensing hoặc phân phối theo license tương thích;
- attribution khả thi ở quy mô record hoặc dataset.

