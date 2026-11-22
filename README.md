# NetLab Signal — LenDinhCungLeTan

Phòng thí nghiệm tương tác để mô phỏng Client–Server, P2P, đa tầng (n-tier), phân tán và SOA. Mỗi mô hình có sơ đồ, giao thức, phương thức truyền, kịch bản lỗi và nhật ký có thể xem lại từng chặng. Mục **Truyền file thật** chạy riêng, hỗ trợ Client–Server và P2P giữa hai trình duyệt.

## Chạy nhanh

1. Cài Node.js (dự án đã kiểm thử với Node.js 24). Mở terminal và chạy `node --version` để kiểm tra.
2. Tải repo bằng **Code → Download ZIP** rồi giải nén, hoặc clone repo bằng Git. Mở terminal tại thư mục chứa `NetLab-Signal.cjs`.
3. Chạy:

   ```sh
   node NetLab-Signal.cjs
   ```

4. Mở **http://localhost:8787** để mô phỏng. Không cần `npm install` hay kết nối Internet sau khi đã có Node.js và tệp dự án. Giữ terminal mở trong lúc demo, nhấn `Ctrl+C` để dừng.

## Demo mô phỏng

Chọn **Phân tán → Chạy kịch bản** để xem Vùng A ngoại tuyến và yêu cầu chuyển sang Vùng B. Bấm một dòng trong **Nhật ký truyền** để xem lại chặng trên sơ đồ. Bạn cũng có thể bật/tắt từng nút, chạy từng bước hoặc đối chiếu hai mô hình.

## Demo truyền file thật trên một máy

1. Mở **http://localhost:8787/transfer.html** trong hai tab.
2. Tab A bấm **Tạo phòng**, tab B nhập mã và bấm **Vào phòng**. Đợi cả hai tab hiện `2/2`.
3. **Client–Server:** chọn file ở tab gửi rồi bấm **Gửi file**. Tab nhận bấm **Tải xuống** trong **Hộp nhận**.
4. **P2P:** chọn P2P ở tab A, bấm **Kết nối P2P**, đợi báo **Đã kết nối trực tiếp**. Chọn P2P ở tab gửi, chọn file và gửi. Tab nhận tải xuống từ hộp nhận.

## Demo trên hai máy

Hai máy phải ở cùng mạng Wi-Fi/LAN tin cậy. Chỉ máy A chạy lệnh Node.js; máy B mở địa chỉ LAN được in trên terminal máy A (dòng Wi-Fi hoặc Ethernet), không dùng `localhost` ở máy B. Tạo phòng và gửi như trên. Nếu Windows yêu cầu cấp quyền tường lửa cho Node.js, chỉ cho phép trên mạng riêng đáng tin cậy. Nếu P2P không kết nối được trên mạng đang dùng, thử lại bằng Client–Server.

File tối đa 20 MiB. Phòng hết hạn sau 30 phút kể từ khi tạo. Bản demo dùng HTTP trên LAN; dùng file mẫu không nhạy cảm và không mở cổng ra Internet. Các mô hình đa tầng, phân tán và SOA chỉ là mô phỏng, không phải chế độ truyền file thật.

## Nếu cổng 8787 đang được sử dụng

Dừng bản NetLab đang chạy bằng `Ctrl+C`, hoặc đặt cổng khác. Ví dụ trên PowerShell:

```powershell
$env:PORT = '8788'
node NetLab-Signal.cjs
```

Sau đó mở `http://localhost:8788`. Nếu `node` không được nhận diện, cài Node.js rồi mở lại terminal.
