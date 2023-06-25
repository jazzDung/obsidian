# Bài tập mở rộng

Đến hạn vào hôm nay lúc 23:59

## Hướng dẫn

Giả sử bạn là một chuyên viên phòng Mô hình, thuộc Khối quản trị rủi ro. Bạn được giao nhiệm vụ phát triển mô hình học máy phục vụ chấm điểm tín dụng để thay thế mô hình chấm điểm tín dụng truyền thống được xây dựng trên mô hình thẻ điểm (scorecard). Mô hình sẽ được sử dụng để phê duyệt mở thẻ Tín dụng nửa cuối năm 2023. Dữ liệu lịch sử được cho như sau:

1. Số lượng khoản vay: 100k khoản vay, 
2. Nhãn tín dụng 0/1 (có hay không số ngày quá hạng ít nhất 90 ngày của bất kỳ kỳ trả nợ nào trong vòng 1 năm quan sát); 
3. 100 đặc trưng (feature) được extract tại thời điểm phê duyệt khoản vay;
4. Khoản vay đến từ 3 sản phẩm thẻ Tín dụng, vay mua ô tô và vay mua nhà với tỷ lệ 40%, 30% và 30%; và tỷ lệ nợ xấu tương ứng là 6%, 3% và 1%;
5. Thời gian phê duyệt khoản vay từ 1/2020 đến 12/2022;

Dựa vào mô hình five step, phân tích sensibility và 2 bài chia sẻ từ các diễn giả ngoài, các bạn sẽ  xây dựng và phân tích độ robustness của mô hình như thế nào để thuyết phục được Giám đốc phòng mô hình và Giám đốc sản phẩm thẻ tín dụng để sử dụng mô hình của các bạn ?

Dear các bạn, chúng ta không có mini-project và điểm quá trình sẽ được đánh giá thông qua các bài tập các chương. Chiều nay **các bạn được ở nhà, không cần đến lớp để làm bài tập mở rộng** như mình vừa tạo. Bài này sẽ có **trọng số rất cao** vì nó thể hiện việc **vận dụng kiến thức** các bạn đã học được và áp dụng vào đúng lĩnh vực các bạn học (DS), vì vậy mong các bạn tập trung và làm cẩn thận. Bài làm cá nhân, ko phải làm theo nhóm. Các bạn làm dưới dạng slide hoặc report trên word, cố gắng giải thích mục đích của các việc các bạn sẽ làm. Mình sẽ mời một số bạn có kết quả tốt chia sẻ trong các buổi sau!






``` bash
python main.py read --config secrets/config.json --catalog integration_tests/configured_catalog.json
```
- source-tcbs-price-history
	- giới hạn 10 ticker tại class organization