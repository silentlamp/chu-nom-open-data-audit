# Kiểm kê dữ liệu mở Chữ Nôm

[![License: CC BY-SA 4.0](https://img.shields.io/badge/t%C3%A0i%20li%E1%BB%87u-CC%20BY--SA%204.0-blue.svg)](https://creativecommons.org/licenses/by-sa/4.0/)
[![Data status](https://img.shields.io/badge/d%E1%BB%AF%20li%E1%BB%87u-audit%20tr%C6%B0%E1%BB%9Bc%20khi%20d%C3%B9ng-orange.svg)](docs/AUDIT.md)

Repository cộng đồng, phi thương mại, dùng để kiểm kê các nguồn dữ liệu, tiêu chuẩn,
phông chữ, corpus và tài liệu học Chữ Nôm; đồng thời xác định nguồn nào có thể tái sử
dụng trong một dự án giáo dục mã nguồn mở.

> **Kết luận hiện tại:** dữ liệu đủ để xây một sản phẩm học Chữ Nôm nghiêm túc,
> nhưng chưa có một bộ dữ liệu duy nhất vừa đầy đủ, được chuẩn hóa thống nhất, vừa có
> giấy phép mở sạch. MVP nên bắt đầu từ Unicode/Unihan, NomNaTong, dữ liệu tự biên
> soạn và các văn bản hết hạn bảo hộ có provenance rõ.

## Nội dung chính

- [Báo cáo audit đầy đủ](docs/AUDIT.md)
- [Danh mục và quyết định sử dụng từng nguồn](docs/SOURCE_CATALOG.md)
- [Mô hình quyền: chữ, dữ liệu, scan, phiên âm, font](docs/RIGHTS_MODEL.md)
- [Quy trình xin phép và mẫu phạm vi cấp phép](docs/PERMISSION_PLAYBOOK.md)
- [Đề xuất lộ trình dữ liệu sạch](docs/ROADMAP.md)
- [Danh mục máy đọc được](data/sources.yaml)
- [Mẫu thư xin phép](templates/permission-request-vi.md)

## Quy ước trạng thái

| Trạng thái | Ý nghĩa |
|---|---|
| 🟢 `green` | Có giấy phép đủ rõ để dùng và phân phối lại khi tuân điều kiện |
| 🟡 `yellow` | Có thể tra cứu/trích dẫn nhưng cần xác nhận trước khi nhập hàng loạt |
| 🔴 `red` | Điều khoản hiện tại không cho phép phân phối công khai theo nhu cầu dự án |

## Phạm vi giấy phép của repository

Tài liệu và metadata **do những người đóng góp vào repository này tự tạo** được phát
hành theo [CC BY-SA 4.0](LICENSE). Mã nguồn được bổ sung trong tương lai có thể dùng
MIT nếu file hoặc thư mục đó ghi rõ.

Giấy phép của repository **không áp dụng** cho tác phẩm, dữ liệu, scan, font hoặc nội
dung của bên thứ ba được nhắc đến. Mỗi nguồn giữ nguyên giấy phép và điều khoản của
chủ sở hữu tương ứng. Repository hiện chỉ chứa metadata, nhận định audit và liên kết;
không chứa bản sao corpus hoặc từ điển hạn chế.

## Trạng thái pháp lý

Audit được cập nhật lần đầu ngày **2026-10-10**. Đây là nghiên cứu vận hành, không
phải tư vấn pháp lý. Mọi quyết định nhập dữ liệu phải kiểm tra lại điều khoản tại thời
điểm sử dụng và lưu bằng chứng giấy phép trong hồ sơ provenance.

## Đóng góp

Xem [CONTRIBUTING.md](CONTRIBUTING.md). Mọi thay đổi trạng thái giấy phép phải kèm
URL nguồn, ngày kiểm tra và bằng chứng đủ để một người khác xác minh độc lập.

