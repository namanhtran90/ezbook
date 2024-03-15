# Bước 1. Xây dựng kịch bản

Chọn chiến dịch cần xây dựng, chỉnh sửa

<figure><img src="../../../.gitbook/assets/image (289).png" alt=""><figcaption></figcaption></figure>

Bước 1: Cài đặt kịch bản

<figure><img src="../../../.gitbook/assets/image (291).png" alt=""><figcaption><p>Bước 1. Cài đặt kịch bản</p></figcaption></figure>

Có thể tự xây dựng kịch bản mới hoặc xây dựng kịch bản theo mẫu hay của các chiến dịch đã chạy trước đó. Bấm nút "Chọn kịch bản mẫu khác" để tham khảo kịch bản của nhiều ngành nghề khác nhau:

<figure><img src="../../../.gitbook/assets/image (580).png" alt=""><figcaption><p>Chọn kịch bản mấu</p></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (581).png" alt=""><figcaption><p>Kịch bản mẫu</p></figcaption></figure>

### Xây dựng kịch bản mới

Thông thường có 2 loại kịch bản:

\- Kịch bản giọng máy thường dùng để xác nhận thông tin khách hàng còn làm tại công ty A không, số điện thoại này phải của anh/chị A không, ...

\- Kịch bản giọng thu âm để giới thiệu sản phẩm dịch vụ, khảo sát nhu cầu của khách

#### 1. Đầu tiên, kéo block Bot nói từ thanh block bên trái ra màn hình botflow.

\- Với kịch bản giọng máy:&#x20;

Sử dụng block Bắt đầu để bắt đầu cuộc gọi trên màn hình botflow.

Kéo Bot nói ra màn hình botflow và tích chọn "Giọng máy": gõ nội dung của Bot nói đầu tiên khi bắt đầu cuộc hội thoại. Ví dụ là nội dung giới thiệu dự án. Các nội dung cá nhân hoá được điền giữa 2 dấu $. Nội dung của các thông tin $gender$, $name$ trong kịch bản được lấy từ các cột trong file excel tải lên.

<figure><img src="../../../.gitbook/assets/image (583).png" alt=""><figcaption><p>Kịch ản giọng máy</p></figcaption></figure>

\- Với kịch bản giọng thu âm: Kéo các block khác nhau từ thanh block bên trái sang màn hình botflow để sử dụng

Sử dụng block Bắt đầu để bắt đầu cuộc gọi trên màn hình botflow.&#x20;

Với mỗi bot nói, bấm "Chọn tệp" để up file ghi âm

<figure><img src="../../../.gitbook/assets/image (582).png" alt=""><figcaption><p>Kịch bản thu âm</p></figcaption></figure>

#### 2. Nối Bot nói vừa tạo với Bot nghe để callbot AI nghe, nhận diện và phân loại nội dung khách hàng nói dựa theo theo các từ khóa.

\- Đặt tên cho block Bot nghe, ví dụ: "Hỏi quan tâm". Sau đó bấm dấu + để thêm các nhóm từ khoá:&#x20;

&#x20;    Nhóm từ khóa "không, sai": trường hợp sai thông tin, khách không có nhu cầu

&#x20;    Nhóm từ khóa "có, ừ, ok, được, nói": trường hợp khách đồng ý trao đổi

&#x20;    Nhóm từ khóa "bận, lát nữa": trường hợp khách trả lời bận không tiện nghe máy

&#x20;    Nhóm im lặng: trường hợp khách hàng không trả lời

&#x20;    Nhóm mặc định sẽ luôn có sẵn để tương tác trong trường hợp khách hàng không trả lời với nội dung ở các nhóm trên

**Note:** T_ừ khóa nhận diện viết thường, không viết hoa, có dấu phẩy và dấu cách sau dấu phẩy._

<figure><img src="../../../.gitbook/assets/image (285).png" alt=""><figcaption><p>Bot nghe</p></figcaption></figure>

\- Với mỗi trường hợp từ khoá của block Bot nghe, ta nối với một block Bot nói với nội dung tương ứng trả lời cho từng trường hợp.

\- Với trường hợp khách hàng im lặng, chúng ta có thể dùng block Bot nói lại để hỏi lại khách hàng có quan tâm tới dự án không.

<figure><img src="../../../.gitbook/assets/image (286).png" alt=""><figcaption><p>Bot nói lại</p></figcaption></figure>

#### 3. Dùng block Gán nhãn theo từng trường hợp của Bot nghe để lọc ra từng nhóm khách hàng khi xuất báo cáo.

<figure><img src="../../../.gitbook/assets/image (287).png" alt=""><figcaption><p>Gán nhãn</p></figcaption></figure>

**Label:**\
_wrong\_number: sai số, không có nhu cầu_

_dong\_y\_trao\_doi: khách hàng có nhu cầu, đồng ý trao đổi_

_busy: khách hàng bận_

_check: KH im lặng, Callbot không nhận diện được do khách hàng nói không có từ khóa đã setup_ \
