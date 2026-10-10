# Audit khả năng tái sử dụng dữ liệu Chữ Nôm

Ngày kiểm tra: **2026-10-10**  
Phạm vi: dự án giáo dục cộng đồng, mã nguồn mở, giúp người Việt nhận mặt chữ và đọc
được phần lớn văn bản Nôm cũng như văn bản tiếng Việt hiện đại được chuyển sang Nôm.

## 1. Kết luận điều hành

Không có một “kho Nôm hoàn chỉnh” có thể tải về và tái cấp phép ngay. Hệ sinh thái
hiện nay bị chia thành nhiều lớp quyền:

1. Mã ký tự và thuộc tính Unicode tương đối mở.
2. Phông NomNaTong có giấy phép MIT rõ ràng.
3. Từ điển, bảng chuẩn hóa và bản số hóa thường chỉ cho xem hoặc sử dụng giáo dục.
4. Corpus OCR lớn thường giới hạn ở nghiên cứu phi thương mại và cấm phân phối lại.
5. Văn bản cổ có thể hết hạn bảo hộ, nhưng scan, phiên âm, bản dịch và chú giải mới
   vẫn có quyền riêng.

Vì vậy dự án khả thi nếu xây theo hướng **provenance-first**: mỗi record phải biết đến
từ nguồn nào, được phép làm gì và bằng chứng giấy phép nằm ở đâu.

## 2. Không được đồng nhất “phi thương mại” với “mở”

Một website miễn phí vẫn là hành vi công bố và phân phối đến công chúng. Một giấy
phép chỉ cho “nghiên cứu phi thương mại” không tự động cho phép:

- đưa toàn bộ dữ liệu lên GitHub;
- tạo API công khai hoặc gói tải offline;
- sửa định nghĩa và phát hành bản phái sinh;
- huấn luyện rồi phát hành mô hình;
- cho người dùng downstream sử dụng thương mại.

Nếu mục tiêu là open source/open data thật sự, văn bản cấp phép nên cho phép cả sử
dụng thương mại downstream, dù tổ chức vận hành dự án vẫn là phi lợi nhuận.

## 3. Cơ sở pháp lý tối thiểu

Luật Sở hữu trí tuệ Việt Nam bảo hộ tác phẩm viết, chương trình máy tính và sưu tập dữ
liệu. Ngoại lệ giáo dục/trích dẫn có phạm vi giới hạn; không phải giấy phép để sao chép
toàn bộ cơ sở dữ liệu. Thời hạn phổ biến đối với tác phẩm viết là suốt đời tác giả cộng
50 năm; quyền nhân thân nhất định được bảo hộ vô thời hạn.

Nguồn tham khảo:

- [Văn bản hợp nhất Luật Sở hữu trí tuệ 11/VBHN-VPQH năm 2022](https://thuvienphapluat.vn/van-ban/So-huu-tri-tue/Van-ban-hop-nhat-11-VBHN-VPQH-2022-Luat-So-huu-tri-tue-556862.aspx)
- [Cục Bản quyền tác giả: giới hạn quyền tác giả](https://cov.gov.vn/tin-tuc/quy-dinh-cua-phap-luat-ve-gioi-han-quyen-tac-gia-168422.html)

## 4. Kết quả theo nhóm nguồn

### 4.1 Unicode, Unihan và IRG — xanh cho data, vàng cho tài liệu

Các file dữ liệu trong Unicode Character Database, Unihan và nhiều dữ liệu công bố
trong các vùng `/Public/`, `/reports/`, `/ivd/data/` được điều chỉnh bởi Unicode
License v3 trừ khi file ghi khác. Có thể sao chép, sửa và phân phối khi giữ notice.

Không được suy diễn rằng PDF tiêu chuẩn, code chart và hình glyph trong PDF cũng có
cùng quyền. Không trích glyph từ code chart và không mirror/sửa PDF nếu chưa được phép.

- [Unicode Licensing Policy](https://unicode.org/policies/licensing_policy.html)
- [Unicode Terms of Use](https://www.unicode.org/copyright.html)
- [Unicode License FAQ](https://unicode.org/faq/unicode_license.html)

**Quyết định:** dùng Unicode/Unihan làm canonical code point và metadata kỹ thuật;
chỉ dẫn link đến PDF/IRG.

### 4.2 NomNaTong — xanh

[Repository NomNaTong](https://github.com/nomfoundation/font) có giấy phép MIT và
phát hành hơn 26.000 glyph. Có thể nhúng, sửa và phân phối lại nếu giữ copyright và
license notice. Nếu sửa glyph đáng kể, nên đổi tên phiên bản để không gây nhầm lẫn.

**Quyết định:** có thể dùng làm font mặc định.

### 4.3 Bảng chữ Hán Nôm Chuẩn Thường dùng — vàng

Bảng được công bố năm 2022, sửa đổi ngày 30/6/2023 và có quy trình tối ưu hóa công
bố năm 2025. Đây là ứng viên quan trọng cho tiếng Việt hiện đại nhưng không phải TCVN
hay một chuẩn quốc gia đã được công nhận. Không tìm thấy giấy phép dữ liệu mở trên
trang công bố.

- [Trang công bố](https://www.hannom-rcv.org/BCHNCTD.html)
- [Bản PDF 2023](https://www.hannom-rcv.org/NS/bchnctd%20300623.pdf)
- [Tối ưu hóa 2025](https://www.hannom-rcv.org/wi/%E6%BA%96%E5%8C%96%3A2025_Revision)
- [PyHanNom ghi nhận quyền dữ liệu gốc](https://pypi.org/project/pyhannom/)
- [Báo cáo hội thảo của University of Tokyo năm 2024](https://www.ealai.c.u-tokyo.ac.jp/en/2024/06/18/report-20240530/)

PyHanNom nêu dữ liệu chỉ dành cho nghiên cứu/giáo dục, cấm sử dụng thương mại và mọi
quyền dữ liệu gốc thuộc Hội Nghiên cứu và Ứng dụng Hán Nôm.

Báo cáo hội thảo của University of Tokyo mô tả đây là một đề xuất cộng đồng quy mô
lớn nhưng chưa được giới học thuật Việt Nam chính thức công nhận. Vì vậy dự án không
nên gắn nhãn “chuẩn chính thức”; nên gọi là một phương án chuẩn hóa và công bố rõ
phiên bản được sử dụng.

**Quyết định:** chưa nhập nguyên bảng. Xin Hội giấy phép bằng văn bản cho CSV/JSON,
sửa đổi, redistribution, API, offline package và downstream commercial use.

### 4.4 Tự Điển Chữ Nôm Dẫn Giải và Nôm Foundation — vàng

Điều khoản website Nôm Foundation cho phép sử dụng công khai phi thương mại nếu kèm
copyright notice và link, nhưng không cấp rõ quyền bulk extraction, sửa đổi và tái cấp
phép thành open dataset.

- [Terms of Use](https://www.nomfoundation.org/About-the-Foundation/Terms-of-use?uiLang=en)
- [Thông tin bản số Tự Điển Chữ Nôm Dẫn Giải](https://www.nomfoundation.org/nom-tools/Tu-Dien-Chu-Nom-Dan_Giai_Sources/About_the_Digital_Version?uiLang=en)

Bản số dựa trên bản in năm 2014 của Nhà xuất bản Khoa học Xã hội. Digitizing Việt Nam
cho biết Nôm Foundation đã giải thể và trao kho lưu trữ cho Columbia University năm
2018, nhưng việc chuyển giao bản lưu trữ không tự động chứng minh đã chuyển toàn bộ
quyền tác giả hoặc quyền cấp phép lại.

Phần giới thiệu của từ điển nêu khoảng 9.200 tự dạng chính, 250 mục phụ lục, 14.519
âm đọc và dẫn chứng từ 124 văn bản nguồn. Đây là nguồn rất lớn cho curriculum, nhưng
cũng cho thấy giá trị sáng tạo nằm ở tuyển chọn, chú giải và liên kết nguồn chứ không
chỉ ở từng ký tự riêng lẻ.

**Quyết định:** tra cứu, đối chiếu và dẫn nguồn được; muốn nhập bulk cần xác nhận chuỗi
quyền với đơn vị quản lý hiện tại, tác giả/chủ thể kế quyền và nhà xuất bản nếu cần.

### 4.5 Digital Library of Hán-Nôm — vàng/đỏ cho phân phối scan

Tác phẩm cổ có thể thuộc phạm vi công cộng, nhưng ảnh scan, phục chế, metadata, phiên
âm, bản dịch, chú giải và alignment có thể có quyền riêng.

- [Dự án thư viện số Hán Nôm](https://nomfoundation.org/nom-project/Digital-Library-of-Han-Nom?uiLang=en)
- [Nguồn tài liệu của Thư viện Quốc gia Việt Nam](https://nlv.gov.vn/ef/information-resources.html)

Trang tài nguyên của Thư viện Quốc gia hiện mô tả khoảng 5.280 đơn vị bản thảo Hán
Nôm; con số này là mô tả quy mô kho, không phải cam kết rằng toàn bộ ảnh và metadata
được cấp phép mở.

**Quyết định:** không tải hàng loạt hoặc phát hành lại scan. Xin Thư viện Quốc gia và
đơn vị quản lý nền tảng. Ưu tiên tự phiên âm và tự chú giải từ nguồn có quyền rõ.

### 4.6 Kho Chữ Hán Nôm Mã Hoá — vàng

Sách của Nguyễn Quang Hồng, xuất bản năm 2007, là nguồn V4 quan trọng cho Unicode.
Không tìm thấy giấy phép mở cho bản sách.

**Quyết định:** dùng mapping tương ứng đã được Unicode công bố; không scan/OCR hay
sao chép toàn bộ bảng/chú thích của sách. Xin Viện Nghiên cứu Hán Nôm, NXB Khoa học
Xã hội và tác giả/chủ thể kế quyền nếu muốn số hóa.

### 4.7 TCVN 5773:1993 và TCVN 6056:1995 — dùng quy tắc, không phát hành tiêu chuẩn

Viện Tiêu chuẩn Chất lượng Việt Nam công bố rằng mình giữ bản quyền xuất bản TCVN.

- [Cổng dữ liệu tiêu chuẩn quốc gia](https://tieuchuan.vsqi.gov.vn/)
- [Thông tin quyền xuất bản/dịch vụ](https://tieuchuan.vsqi.gov.vn/goi-dich-vu)

**Quyết định:** được dẫn số hiệu, mô tả và tự viết converter; không đưa PDF hoặc ảnh
chụp toàn bảng lên repo. Nếu cần nguyên bảng, xin VSQI.

### 4.8 CJKVI IDS — xanh có copyleft

[cjkvi-ids](https://github.com/cjkvi/cjkvi-ids) ghi `ids.txt` theo điều khoản CHISE và
đa số dữ liệu khác theo GPLv2. Đây là nguồn hữu ích để dạy cấu tạo chữ.

**Quyết định:** giữ thành dataset/module độc lập, giữ notice và GPL; không đổi thành
MIT hoặc CC BY-SA và không trộn không thể tách với dữ liệu có license xung đột.

### 4.9 Nôm Na Việt và RIME — xanh/vàng tùy thành phần

[rime-nom-viet](https://github.com/nomnaviet/rime-nom-viet) có LICENSE MIT, hơn
100.000 entry và khoảng 46.000 từ ghép. README cũng nói dữ liệu được xuất một phần từ
database Nôm Na Việt. Cần xác nhận MIT áp dụng cho toàn bộ file từ điển và provenance
upstream đã sạch.

[nomnaviet-contrib](https://github.com/nomnaviet/nomnaviet-contrib) nói contribution
theo cùng license với dự án chính nhưng không nêu license cụ thể.

**Quyết định:** có thể nghiên cứu và thử nghiệm; trước khi nhập bulk, yêu cầu maintainer
xác nhận bằng văn bản phạm vi MIT và nguồn của từng nhóm entry.

### 4.10 chunom.org — vàng

[chunom.org](https://chunom.org/) có từ điển, cấp độ học, tần suất và IDS nhưng không
tìm thấy giấy phép dữ liệu chung. Free access không phải là quyền scrape/repackage.

**Quyết định:** chỉ đối chiếu và dẫn link; xin chủ quản trước khi nhập dữ liệu.

### 4.11 NômFlow / Digitizing Việt Nam — vàng

[Digitizing Việt Nam](https://www.digitizingvietnam.com/en) cung cấp collection và
tài nguyên sư phạm miễn phí, nhưng không thấy license mở áp dụng chung. Dự án do
Columbia University và Fulbright University Vietnam phối hợp.

**Quyết định:** xin phép trước khi chuyển curriculum hoặc data sang bài học của dự án.

### 4.12 IHR-NomDB — đỏ cho open redistribution

[IHR-NomDB](https://morphoboid.labri.fr/ihr-nom.html) chỉ cho sử dụng nghiên cứu phi
thương mại và hạn chế sao chép/công bố/phân phối annotation.

Nguồn này mô tả 34.991 mẫu viết tay, 704.991 mẫu tổng hợp và từ vựng 13.254 ký tự.
Quy mô lớn không thay đổi giới hạn phân phối.

**Quyết định:** không đưa ảnh hay annotation vào GitHub/open dataset. Chỉ dùng nội bộ
theo điều khoản hoặc xin giấy phép mới từ nhóm nghiên cứu và chủ nguồn ảnh.

### 4.13 NomNaOCR — đỏ cho đến khi làm sạch chuỗi quyền

[NomNaOCR](https://github.com/ds4v/NomNaOCR/blob/main/README_en.md) mô tả việc thu thập
ảnh và phiên âm từ tài liệu do VNPF số hóa, sau đó tạo bounding box và patch OCR.
Quyền của annotation mới không xóa quyền ở ảnh/phiên âm upstream.

README công bố 2.953 trang và 38.318 patch được gán nhãn. Đây là dữ liệu nghiên cứu
hữu ích nhưng chưa có chuỗi giấy phép đủ sạch cho một bản phát hành mở tổng hợp.

**Quyết định:** không mirror dataset. Muốn dùng công khai phải có xác nhận của nhóm
NomNaOCR và các chủ thể của ảnh/phiên âm upstream.

### 4.14 Bài báo, giáo trình đại học và tài liệu Viện Hán Nôm — vàng

Có thể dẫn nguồn, tóm tắt phương pháp và trích dẫn hợp lý. Không sao chép nguyên bài,
bảng, hình hoặc biến giáo trình thành nội dung tương tác mà chưa xin tác giả và đơn vị
phát hành.

**Quyết định:** học nguyên lý rồi tự viết curriculum; xin phép riêng khi tái sử dụng
biểu đạt, bảng phân loại, hình hoặc bài tập.

Nguồn khởi đầu để khảo sát chương trình học và phương pháp, không phải để sao chép:

- [Viện Nghiên cứu Hán Nôm](https://hannom.vass.gov.vn/)
- [Khung/chương trình đào tạo được USSH công bố](https://ussh.vnu.edu.vn/uploads/ussh/dao-tao/2023_02/230106dchp-dieu-chinh-nganh-van-hoc-ctdt-2019-dieu-chinh-nam-2022.pdf)

### 4.15 Văn bản cổ — xanh ở lớp tác phẩm, vàng ở lớp ấn bản

Truyện Kiều, Lục Vân Tiên và nhiều tác phẩm cổ có thể đã hết thời hạn bảo hộ ở lớp tác
phẩm gốc. Tuy nhiên mỗi bản scan, phiên âm, hiệu khảo, dịch, chú giải hoặc alignment
hiện đại phải được audit riêng.

**Quyết định:** dùng nguồn vật lý/public-domain có căn cứ, tự tạo transcription,
alignment và annotation rồi phát hành lớp mới dưới giấy phép mở.

## 5. Đánh giá tính đầy đủ của dữ liệu

Dữ liệu hiện có đủ để:

- hiển thị phần lớn chữ Nôm đã mã hóa;
- tra chữ theo âm, mã, thành phần và dị thể;
- xây curriculum nhận mặt chữ;
- tạo bộ gõ và converter thử nghiệm;
- xây corpus đọc cổ điển ở quy mô có kiểm soát.

Chưa đủ sạch để tuyên bố:

- bao phủ “toàn bộ chữ Nôm”;
- có một cách viết duy nhất cho mọi từ tiếng Việt hiện đại;
- mọi mapping âm–chữ đều là đồng thuận học thuật;
- corpus OCR hiện có có thể tái phân phối tự do;
- một bảng chuẩn hiện hành là chuẩn quốc gia.

## 6. Khuyến nghị phát hành

- Code: MIT hoặc Apache-2.0.
- Tài liệu và bài học tự biên soạn: CC BY-SA 4.0.
- Database gốc của dự án: cân nhắc CC BY-SA 4.0 hoặc ODbL-1.0.
- Font: giữ nguyên MIT của NomNaTong.
- CJKVI: giữ GPL theo upstream, đóng gói tách biệt.
- Không tái cấp phép nguồn bên thứ ba nếu không có quyền rõ ràng.
- Mỗi record phải có `source_id`, `license`, `retrieved_at`, `evidence_url` và
  `redistribution_status`.

