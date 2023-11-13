## Utils
### get_proxy_url
- Convert link báo -> Proxy link để không bị ban IP
- URL gốc nằm ở sau cái flag &url: https://proxy.scrapeops.io/v1/?api_key=784f2906-0dba-4323-aff9-6bc4ebe21bd1&url=https%3A%2F%2Fnguoiquansat.vn%2Fhe-lo-he-sinh-thai-khung-phia-sau-2-sep-lon-kin-tieng-cua-vndirect-87891.html'

### get_original_url
- Tách lấy cái URL gốc của bài báo từ Proxy URL ở trên

### get_proxy_relative_url
- Giống get_proxy_url nhưng mà cho [[URL#Absolute URL]]
- Tự lọc lấy absolute URL, sau đó gắn thêm relative URL vào đít

``` python
get_proxy_relative_url('https://proxy.scrapeops.io/v1/?api_key=784f2906-0dba-4323-aff9-6bc4ebe21bd1&url=https%3A%2F%2Fnguoiquansat.vn%2Fhe-lo-he-sinh-thai-khung-phia-sau-2-sep-lon-kin-tieng-cua-vndirect-87891.html', 'images/lmao.jpg')

-> 
'https://proxy.scrapeops.io/v1/?api_key=784f2906-0dba-4323-aff9-6bc4ebe21bd1&url=https%3A%2F%2Fnguoiquansat.vn%2Fimages%2Flmao.jpg'
```


### get_deltafetch_key
- Lấy phần path của URL báo, với mục đích chính là để store trong db và không crawl lại những lần sau
``` python
get_deltafetch_key('https://nguoiquansat.vn/lmao/he-lo-he-sinh-thai-khung-phia-sau-2-sep-lon-kin-tieng-cua-vndirect-87891.html')

-> 'he-lo-he-sinh-thai-khung-phia-sau-2-sep-lon-kin-tieng-cua-vndirect-87891.html'
```

### origin_urlparse_cached
- Chịu

### is_link_image
- Check xem resource đọc được có phải ảnh không bằng cách xem đuôi file
- '.png', '.jpg', '.jpeg', '.tiff', '.bmp', '.gif'

### extract_img_url_from_css
- Hàm này áp dụng cho từng cell trong 1 block CSS
- Mình sẽ cho 1 list các CSS selector, hàm sẽ tìm resource trong các CSS của cell
- Nếu tìm thấy 1 ảnh (Check bằng hàm is_link_image) thì break và trả về luôn url ảnh đầu tiên tìm được

### extract_text_from_css
- Hàm này áp dụng cho từng cell trong 1 block CSS và 1 CSS selector
- Mình sẽ cho CSS selector, hàm sẽ tìm tất cả resource trong các CSS của cell
- Ngoài ra thay các \r \n bằng dấu cách, xuống dòng các kiểu

### replace_attr
- Thay attr trong HTML bằng 1 attr khác

``` python

html_doc = '<img src="https://nqs.1cdn.vn/thumbs/540x360/2023/08/25/dautu.kinhtechungkhoan.vn-stores-news_dataimages-2023-082023-25-08-in_social-_mia-du20230825083841.png"'  

replace_attr(html_doc, 'src', 'lmao')

-> 
'<img lmao="https://nqs.1cdn.vn/thumbs/540x360/2023/08/25/dautu.kinhtechungkhoan.vn-stores-news_dataimages-2023-082023-25-08-in_social-_mia-du20230825083841.png"'
```

### strip_tags()
- Xoá tag trong HTML (Toàn bộ tag và resource)

``` python

html_doc = '<a href="https://nguoiquansat.vn/tang-140-sau-8-thang-1-co-phieu-duong-cho-diem-mua-tai-vung-dinh-5-nam-87635.html"><img src="https://nqs.1cdn.vn/thumbs/540x360/2023/08/25/dautu.kinhtechungkhoan.vn-stores-news_dataimages-2023-082023-25-08-in_social-_mia-du20230825083841.png" alt="Tăng 140% sau 8 tháng, 1 cổ phiếu đường cho điểm mua tại vùng đỉnh 5 năm" title="Tăng 140% sau 8 tháng, 1 cổ phiếu đường cho điểm mua tại vùng đỉnh 5 năm"></a>'  

replace_attr(html_doc, 'src', 'data-src')

->
'<a href="https://nguoiquansat.vn/tang-140-sau-8-thang-1-co-phieu-duong-cho-diem-mua-tai-vung-dinh-5-nam-87635.html"></a>'
```


### get_clean_text
- Trích toàn bộ text trong cell

```
html_doc = '<p>Bà <a href="https://dulieu.nguoiquansat.vn/ca-nhan-nqs_8120/pham-minh-huong" target="_blank" rel="nofollow">Phạm Minh Hương</a> rời ghế Chủ tịch HĐQT của Chứng khoán VnDirect (mã chứng khoán <a href="https://dulieu.nguoiquansat.vn/doanh-nghiep/VND" target="_blank" rel="nofollow">VND</a>) mấy tháng trước là sự kiện rất được quan tâm trên thị trường thời điểm đó. Nguyên nhân cũng bởi đây là lần đầu VnDirect thay tướng trong 17 năm. Sau khi rời ghế Chủ tịch, bà Minh Hương quay về ngồi ghế Tổng Giám đốc.</p>'  
  
soup = BeautifulSoup(html_doc, 'html.parser')  
get_clean_text(soup)

->
'Bà. Phạm Minh Hương. rời ghế Chủ tịch HĐQT của Chứng khoán VnDirect (mã chứng khoán. VND. ) mấy tháng trước là sự kiện rất được quan tâm trên thị trường thời điểm đó. Nguyên nhân cũng bởi đây là lần đầu VnDirect thay tướng trong 17 năm. Sau khi rời ghế Chủ tịch, bà Minh Hương quay về ngồi ghế Tổng Giám đốc.'
```


kubesphere 