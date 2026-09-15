Báo cáo Phân tích Dự án Mã nguồn mở: Sự rẽ nhánh của Redis và sự ra đời của Valkey
1. Giới thiệu tổng quan
Trong hệ sinh thái phần mềm mã nguồn mở (FOSS), tính minh bạch và sự tin tưởng giữa đơn vị quản trị dự án cùng cộng đồng đóng vai trò then chốt. Tuy nhiên, khi lợi ích kinh doanh thương mại va chạm với tinh thần tự do của mã nguồn mở, mâu thuẫn là điều khó tránh khỏi. Trường hợp điển hình gần đây nhất chính là cuộc khủng hoảng xung quanh Redis vào tháng 03/2024, dẫn đến sự ra đời của bản rẽ nhánh (fork) mã nguồn mở hoàn toàn mang tên Valkey.

2. Nguyên nhân mâu thuẫn
Redis vốn là một cơ sở dữ liệu lưu trữ cấu trúc dữ liệu trên bộ nhớ trong (in-memory data store) cực kỳ phổ biến, được phát hành từ năm 2009 dưới giấy phép BSD 3-Clause — một giấy phép mã nguồn mở rất thông thoáng, cho phép bất kỳ ai thương mại hóa hoặc nhúng vào sản phẩm riêng.

Mâu thuẫn bùng nổ khi công ty Redis Inc. (đơn vị nắm quyền quản trị chính) thông báo thay đổi giấy phép bản quyền kể từ phiên bản Redis 7.2.4 trở đi:

Chuyển đổi giấy phép: Chuyển từ BSD 3-Clause sang mô hình cấp phép kép (Dual-license) gồm RSALv2 (Redis Source Available License) và SSPLv1 (Server Side Public License).

Mục đích: Ngăn chặn các nhà cung cấp dịch vụ điện toán đám mây lớn (như AWS, Google Cloud, Microsoft Azure) bán lại Redis dưới dạng dịch vụ quản lý (managed service) mà không đóng góp doanh thu hoặc mã nguồn ngược lại cho Redis Inc.

Hậu quả: Việc thay đổi này làm cho Redis chính thức không còn là phần mềm mã nguồn mở theo định nghĩa chuẩn của Tổ chức Mã nguồn mở (OSI - Open Source Initiative), làm tổn hại nghiêm trọng đến lòng tin của cộng đồng lập trình viên và các doanh nghiệp đang tích hợp Redis vào hệ sinh thái của họ.

3. Quá trình rẽ nhánh và sự ra đời của Valkey
Ngay sau quyết định của Redis Inc., cộng đồng phát triển mã nguồn mở đã phản ứng nhanh chóng để bảo vệ một công cụ hạ tầng quan trọng:

Khởi xướng dự án: Các kỹ sư hàng đầu từng đóng góp cho Redis tại AWS, Google Cloud, Uber, Ericsson và các tập đoàn công nghệ khác đã liên kết để tạo ra một bản fork từ phiên bản Redis 7.2.4 (phiên bản cuối cùng còn dùng giấy phép BSD).

Sự bảo trợ của Linux Foundation: Dự án fork này nhanh chóng nhận được sự bảo trợ chính thức từ Linux Foundation — tổ chức uy tín hàng đầu thế giới về phần mềm mã nguồn mở — và được đặt tên chính thức là Valkey.

Định hướng phát triển: Valkey duy trì giấy phép BSD 3-Clause nguyên bản, cam kết phát triển hoàn toàn theo mô hình cộng đồng (community-driven), độc lập với bất kỳ chương trình nghị sự thương mại của một công ty đơn lẻ nào.

4. Tác động và bài học kinh nghiệm
Sự kiện Redis rẽ nhánh sang Valkey mang lại nhiều bài học đắt giá cho ngành công nghiệp phần mềm:

Đối với dự án Redis: Redis Inc. phải đối mặt với sự quay lưng của cộng đồng chuyên môn. Nhiều hệ điều hành Linux lớn (như Fedora, Debian) và các dịch vụ đám mây đã bắt đầu lên kế hoạch loại bỏ Redis để chuyển sang tích hợp Valkey.

Đối với cộng đồng mã nguồn mở: Sự ra đời của Valkey cho thấy sức mạnh của cơ chế "Fork" trong FOSS. Khi một công ty muốn độc chiếm một công cụ chung, cộng đồng hoàn toàn có quyền lực và năng lực để duy trì phiên bản tự do cho toàn thế giới.

Bài học về quản trị: Các dự án hạ tầng cốt lõi nên được quản lý bởi các tổ chức phi lợi nhuận trung lập (như Linux Foundation hay CNCF) ngay từ đầu để tránh rủi ro bị thâu tóm thương mại hóa trong tương lai.
