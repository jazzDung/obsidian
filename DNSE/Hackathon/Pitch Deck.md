![[Pasted image 20230807164507.png]]

## 2. Problem
- Người dùng mới không biết đầu tư
- Người dùng mới không biết sử dụng AI broker

## 3. Solution
- Một người đồng hành có khả năng hướng dẫn người dùng mới
- Có khả năng đưa ra feedback sau mỗi hành động của người dùng

## 4. Market size and opportunity
- Apply được cho toàn bộ tập khách hàng mới bắt đầu đầu tư
- Thậm chí có thể apply cho những người chưa từng đầu tư

## 5. Product / Services
- Trademate
	- 1 con bot tích hợp vào app Entrade
	- 

## 6. Process

- User
- Liên kết dl người dùng vào con chat
- Hướng dẫn đặt lệnh
- Dành cho người dùng mới
	- Vấn đề rất lớn: Rất nhiều người đăng ký app -> Nhưng không bỏ tiền -> Không biết đầu tư
	- AI broker: Người mới không biết phải đặt câu hỏi -> Trademate sẽ hướng đến người dùng: Đồng hành ngay từ đầu app, hướng dẫn cho người dùng về các câu cần hỏi
	- Không cần người dùng vào app -> Bot vẫn sẽ gửi các gợi ý dạy về đầu tư.
	- Nhấn mạnh: Chia sẻ với nhà đầu tư về cảm xúc/ kinh nghiệm
		- Sau khi đầu tư -> Cùng phân tích vì sao lại lãi và lỗ, có thêm chúc mừng/RIP
		- Khi mà lỗ -> Chia sẻ về lí do fail -> Chỉ ra cần nhìn vào đâu, làm gì để sau trade thành công
	- Chú trọng vào việc interactive với người dùng giống 1 con AI thực thụ, không phải kiểu hỏi đáp'
	- AI take care người dùng -> Quá trình dài -> Trong ngày đó tập trung demo vào trải nghiệm người dùng, các AI chào đón, hướng dẫn người dùng
	- Đặt lệnh -> Bắn lên API -> Con bot tự đặt câu hỏi và tự trả về câu trả lời cho con Trademate để nó trả lời
	- Thay vì cửa sổ chat -> Thay bằng bubble chat -> để trademate có thể interactive với người dùng mọi lúc mọi nơi mà không làm ảnh hưởng đến flow tương tác với app của người dùng.
- 2 cách demo
	- Em là người bắt đầu giao dịch -> Cách Trademate hỗ trợ người mới
	- Giấu demo với người dùng pros đi, khi giám khảo hỏi -> Show ra, giám khảo shock chết
	- Cố gắng có tính năng gì đó functional trong hack day -> 
	- Tạo app flutter riêng -> Fake 1 cái frame chat vào thành 1 cửa sổ trong app Entrade
	- Tạo chat web -> Có vẻ không chọn phương án này
	- Show tất cả các case người dùng -> Và cho thấy cách trademate giúp cho người dùng.
	- Show demo nhiều thời gian -> Lịch sử tin nhắn qua nhiều ngày -> Thể hiện quá trình Trademate dần lấy lòng tin người dùng bằng small talk, dần làm quen, take care
- Với pros
	- Lấy dl của họ, phân loại thành các category dựa trên loại đầu tư -> 
	- Học hỏi các câu hỏi của pros (Actively bằng cách hỏi xem họ cần thêm gì không, gợi ý) -> Tự cải thiện reports cho họ
	- Có thể cho tập này vào future works
- Sale
	- Có thể ra dollar bill, có thể bán cho các bên thứ 3
	- Sẽ nói về khung kiến trúc -> Đảm bảo nó có thể đứng độc lập như 1 ứng dụng riêng -> Không phải extension ứng dụng có sẵn
	- Định giá sản phẩm -> 
- So sánh với AI Broker
	- Có chữ broker -> Rào cản với người dùng, 
	- Nói chuyện với nhà đầu tư -> Biết về khả năng người dùng (Đặt câu hỏi lúc nào)
	- Cần có cách interactive với người dùng kể cả khi họ chưa có ý định đầu tư
		- Demo em chào anh ạ -> Anh ăn cơm chưa
	- Dựng video chat với người dùng
		- Dùng meme bò và gấu
		- Mấy câu hỏi trendy tếu tếu
		- Than nghèo kể khổ, gợi người dùng kể về tình hình tài chính

1. Nỗi đau user -> Kể chuyện, kể case đau khổ,  không biết giao dich, cty có AI broker nhưng khong biết hỏi, không biết dùng
2. Trademate -> Đồng hành với người đầu tư mới, giới thiệu thị trường, mã -> Rút ngắn thời gian học bằng việc học qua lỗi, học qua trải nghiệm, review lại về performance của họ, các sai lầm, những thứ đã làm đúng, personalized learning, KHÔNG CẢN người dùng khi mua, chỉ phân tích khi đã mua sai -> Cho người dùng cảm giác được quan tâm, vì nhà đầu tư thường cô đơn (Không có ai để chia sẻ khi mất tiền, vui khi có tiền)
3. Revenue công ty -> Phân tích về target demographic, độ tuổi, phân tích vì sao họ dùng app nhưng dừng đầu tư/ không nạp tiền -> Họ sợ, họ không biết đầu tư, họ không biết mình lỗ lãi ra sao 
4. Phân tích con số cty bỏ bao nhiêu tiền cho 1 nguời dùng -> So sánh với việc người dùng đăng ký nhưng không thật sự 
5. Khác biệt giữa AI broker -> Không khuyên bạn mua, cho bạn biết kết quả khi giao dịch, đưa ra lời chúc mừng/an ủi dựa vào kết quả, đưa ra bài học -> Hướng người dùng làm tốt hơn, đánh vào tâm lý con người -> Đánh vào cảm xúc
6. Người dùng thua lỗ nhiều -> Trademate khuyên người dùng, vẽ ra 1 cái roadmap an toàn cho người dùng
7. 90% lỗ -> Là những người mà cần Trademate
8. Đánh vào imposter syndrome -> Trademate cho thấy người dùng đánh giá đúng về quyết định của mình
9. Người dùng có thể chia sẻ lý do đầu tư với Trademate -> Có thể dùng để phân hạng người dùng

## Trong thời gian nghiên cứu ngắn -> Có thể có sai sót, nhưng các selling point là valid
# Chia việc
- Lên pitch deck - Dũng
- Dựng video cap lại chat trong nhiều ngày - Tính sau
- Mock app chat trong Entrade, bubble chat. - Thi
- Implement action layer nhận tín hiệu đầu tư để trả câu hỏi và chọc vào AI Broker - Dũng + Trung
- Kể chuyện
	- Small talk - Thi
	- Phân tích sau khi mua - Trung
	- Phân tích sau khi bán (chúc mừng, an ủi) - Trung
	- Phân tích tóm tắt hiệu quả đầu tư của người dùng, nhưng mà theo kiểu small talk, không show bảng biểu - Đức


Phần Giải pháp

Dẹp xác định thị trường

Vì sao người dùng nên trả tiền cho chatbot
- Tích hợp vào mặt demo
- Nói về việc 

Phần lớn để thêm vào
- Demo
- Roadmap tính năng (Chia các stage)
- Kiến trúc, nói 2 ảnh anh gửi
- Kế hoạch đi ra thị trường
- Phần gọi vốn, doanh thu -> Nói thêm
- Nói về team của em có những ai, nói về việc đầu tư ở đây 


### Slide 1
Xin chào, em là Dũng, và đây là team Last Man Standing

### Slide 2
Trước khi bàn đến sản phẩm của team, chúng ta hãy cùng trả lời câu hỏi, vấn đề lớn nhất của việc đầu tư là gì.

Đó chính là sự rủi ro, trong số những nhà đầu tư đã mở tài khoản, chỉ có 8% thực sự phát sinh lệnh đặt, và trong số những lệnh đặt đó, chỉ có 10% có lãi

### Slide 3
Vậy làm thế nào để giải quyết vấn đề này?
Hay là chúng ta cho mỗi nhà đầu tư một người bạn tri kỷ?

### Slide 4
Người bạn đó chính là trademate


### Slide 6
Vậy cụ thể, Trademate sẽ làm gì?

Như chúng ta đã nói, nhiều nhà giao dịch gặp khó khăn với việc phân tích hậu giao dịch, họ không hiểu vì sao quyết định đầu tư của bản thân lại dẫn đến thua lỗ.

Trademate sẽ ở đó để giúp chúng ta hình thành thói quen phân tích các quyết định bản thân sau khi đã có kết quả

Một trong những lí do khiến người dùng khó phân tích các quyết định của. bản thân, là vì những quyết định đó phần lớn bị ảnh hưởng bởi định kiến, bởi cảm xúc.

Trong những trường hợp như vậy, Trademate sẽ là 1 chốt chặn, cung cấp cho người dùng những phản hồi khách quan để giúp họ có thể đưa ra các quyết định tốt hơn trong tương lai

### Slide 7
Đó là về khía cạnh chuyên môn, dù có chuẩn bị đến mấy ta cũng không thể tránh khỏi sai sót.

Và những lúc như vậy, Trademate sẽ là người đầu tiên động viên, chia sẻ với nhà đầu tư, giúp họ ổn định tinh thần, và tiếp tục đầu tư với những quyết định sáng suốt hơn.

Và những lúc chúng ta thành công, Trademate sẽ là người đầu tiên chúc mừng chúng ta, và nhắc lại về những gì họ đã làm đúng, để họ có thể tiếp tục làm những gì họ đang làm tốt

### Slide 8
Những vấn dề với đầu tư chứng khoán đã tồn tại từ rất lâu, nhưng tại sao bây giờ mới là lúc để một sản phẩm như Trademate xuất hiện.

### Slide 9
Có 3 yếu tố chính

Đầu tiên, chúng ta đang sống trong giai đoạn mà mọi ngừoi đã dần quen với các sản phẩm AI, chatbot nói chung, và các sản phẩm công nghệ nói riêng, khiến cho quá trình xâm nhập thị trường của Trademate đang trở nên rõ ràng bao giờ hết.

Lí do thứ 2, hiện nay sức khoẻ tinh thần đang là một trong những lĩnh vực được quan tâm hàng đầu hiện nay, và một sản phẩm có thể giải quyết những vấn đề về sức khoẻ tinh thần, là một sản phẩm có khả năng thành công cao

Và lí do rõ ràng nhất, là người dùng đang có sự quan tâm đến đầu tư chứng khoán hơn bao giờ hết, kiến thức đã có thể tiếp cận ở khắp mọi nơi, thứ mà họ còn thiếu để bắt đầu là một người đồng hành.

### Slide 10
Trademate là một sản phẩm tham vọng, vậy chúng ta phải có một khung kiến trúc đủ thực tế để có thể hiện thực hoá những tính năng của Trademate.

Trademate sẽ hoạt động trong 2 viễn cảnh chính.

Trường hợp đơn giản nhất, Trademate sẽ nhận câu hỏi từ người dùng. Tại đây, câu hỏi, lời nhắn của họ sẽ đi qua một mô hình phân loại để xác định trường ý nghĩa của nội dung chúng ta đang làm việc là gì. Khi chúng ta xác định được một câu hỏi liên quan đến chứng khoán, chúng ta sẽ đi qua một logic để quyết định những thông tin cần thiết để xây dựng lên phản hồi của Trademate, và chúng ta sẽ gọi API để lấy thông tin cần thiết, sau đó một mô hình ngôn ngữ như ChatGPT sẽ tổng hợp nên phản hồi và gửi lại cho người dùng

### Slide 11
Trường hợp thứ 2, chúng ta muốn Trademate chủ động tương tác với người dùng

Trademate sẽ dựa vào những dữ liệu người dùng và các dữ liệu thị trường, trải qua một mô hình, đưa ra một danh sách các tương tác có thể thực hiện. Tất nhiên chúng ta muốn trademate suy nghĩ như một người dùng, và chỉ tương tác những gì thật sự cần thiết, và trên hết, là đúng thời điểm. Vậy nên những tương tác ở đây sẽ được đi qua vài lớp mô hình để xếp hạng theo mức độ liên quan, cần thiết. Và những tương tác đạt đủ điều kiện chúng ta đặt ra sẽ được thực hiện với người dùng


### Slide 12


Vậy với bộ khung đó, chúng ta sẽ bắt đầu phát triển từ những tính năng gì?

Chúng ta sẽ bắt đầu từ những phân tích giao dịch cơ bản. Tại giai đoạn này những phẫn tích của Trademate sẽ dựa trên các quy tắc đã định trước.

Những tương tác chia sẻ về mặt tinh thần với người dùng cũng sẽ xuất hiện ở giai đoạn đầu tiên. Chúng ta sẽ bắt đầu với những thông điệp khích lệ, chúc mừng có thể áp dụng cho mọi người dùng

Tất nhiên, giai đoạn đầu sẽ cần nhiều cải thiện, nên chúng tôi sẽ thu thập phản hồi từ người dùng để cải thiện khả năng của Trademate trong tương lai

### Slide 13
Một khi đã đạt được những tính năng cơ bản
Chúng ta sẽ nhắm đến sự cá nhân hoá, ta muốn nhà đầu tư thực sự cảm thấy Trademate như một người bạn được thiêt kế dành riêng cho mình

Đầu tiên Trademate sẽ nhận diệnj được những xu hướng đầu tư lặp lại của người dùng mà dẫn đến kêt quả xấu, và từ đó đưa ra các phản hồi có tính xây dựng để họ có thể cải thiện

Những lộ trình đầu tư mà Trademate đưa ra cũng sẽ được tối ưu cho từng người dùng.

Và cuối cùng, những phản hồi của Trademate cũng sẽ được cải thiện, và tinh chỉnh dựa trên những gì người dùng đã phản hồi, và nhữg dữ liệu chúng ta ghi nhận trong quá trình sử dụng của ngừoi dùng

### Slide 14
Bước tiếp theo, đó là gamification.
Trademate là một người bạn đòng hành, nhưng ở góc nhìn của những nền tảng chứng khoán. Trademate ;à một thứ vũ khi để thúc đẩy người dùng đầu tư

Và không gì thúc đẩu người dùng hơn sự cạnh tranh








Len kubesphere
uat-linux -> tim space 

Banrg investor_codelist bi permission denied
