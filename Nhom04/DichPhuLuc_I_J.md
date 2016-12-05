#Phần I: Đặc tả thiết kế kiểm thử

**Thiết kế kiểm thử**
Hệ thống của chúng tôi có các chức năng sau:
•	Administrator
•	Đăng ký và mở rộng
•	Truy cập trên web-site
•	Phàn nàn
Trong trường hợp kiểm thử, các tài liệu nên được sắp xếp theo chức năng. Các điều kiện kiểm thử sau các thẻ tài liệu, cái mà mô tả tiêu chuẩn chấp nhận của tài liệu, nên được bao phủ.

**Đặc tả thiết kế kiểm thử**
Để làm cho dễ hiểu hơn, đặc tả thiết kế kiểm thử dựa vào cơ sở nào, một trích đoạn yêu cầu hệ thống cho các phần PC của UV/TIT-14 33a được đưa vào đây.

##Đặc tả yêu cầu hệ thống cho các phần PC của UV/TIT – 14 33a

###4.1	Cài đặt

Hệ thống sẽ có một menu cài đặt với các lựa chọn sau:
+ Cài đặt băng tải
+ Cài đặt hiệu chuẩn
+ …

###4.2	Cài đặt băng tải

**4.2.1. Các thông số sau cần phải cài đặt:**

+ Max speed (mm/s)
+ Min speed (mm/s)

**4.2.2. Sau khi thực hiện thay đổi cài đặt, hệ thống sẽ hiển thị một trong các thông báo sau:**

+ Setup done
+ Max speed ngoài khoảng cho phép
+ Min speed ngoài khoảng cho phép
Hệ thống cho phép người dùng thoát khỏi việc cài đặt mà không thay đổi thông tin gì.

###4.8 Phân tích

Hệ thống cho phép người dùng đặt một số loại phân tích để thực hiện. Các loại phân tích được đưa ra ở bảng 6.
Hệ thống cho phép một số ví dụ về khoảng max/min speed ở bảng 6. Kết quả ngoài khoảng này là không hợp lệ.
Hệ thống sẽ hiển thị một số kết quả dựa vào việc tìm kiếm “Accepted”, “Warnig”, “Alarm”. Giá trị được đưa ra ở bảng 6.

 | Loại | Phạm vi đo lường | Chấp nhận lớn nhất | Cảnh báo lớn nhất | Giá mẫu |
| --------- | ---- | ------- | ---------------- | ---------- |
| NCS | 2 - 315 incl | 65 | 270 | 0.35€ |
| C2O | 0.01 - 0.89 incl | 0.3 | 0.65 | 0.40€ |
| NCS | 2 - 315 incl | 65 | 270 | 0.35€ |
| NCS | 2 - 315 incl | 65 | 270 | 0.35€ |

Hệ thống sẽ chắc chắn rẳng định dạng của các ví dụ dưới đây là đúng trước khi một ví dụ được thực hiện.
Sample no. = T”–“n[n]”-“nnn”-“dd”.”mm“.“yy 
Where:

- T = “A” | “S” | “M” 
- n = numbers from 0 – 9 
- dd = numbers from 01 – 31 
- mm = numbers from 01 – 12 
- yy = numbers from 00 – 99

Hệ thống sẽ chấp nhận một số ví dụ bao gồm 4 phần chia bởi dấu gạch nối, tên tương ứng là:
•	Action type (A, S hoặc M)
•	Sample type (1 hoặc 2 chữ số)
•	Sample id (3 chữ số)
•	Ngày mà ví dụ được lấy
Giải thích:
Khi ví dụ được nhập vào máy, máy đọc số nhưng bỏ qua thông tin ngày.
Cách mà máy xem xét ví dụ phụ thuộc vào “action type”. Trong trường hợp tự động sử lý một vị trí để in báo cáo, trong khi 2 vị trí cho 0 báo cáo. Để tự động sử lý, sample type xác định cách phân tích được thực hiện. Sample type không quan trọng trong trường hợp phân tích thủ công.
Khi tự động phân tích được thực hiện và kết quả đặt dưới sample id. Nếu sample id không tìm thấy ở CSDL thì phân tích không được thực hiện và hiển thị thông báo lỗi
Để có thể chạy phân tích tự động, id cần được tìm thấy trong CSDL.
Trường hợp thủ công, người dùng chọn từng bước một cách rõ ràng. Người dùng phải viết báo cáo với kết quả bằng văn bản, cái mà được in ra khi phân tích kết thúc.
###4.13 Hoạt động mở nắp (Lid Operation)

**4.13.1 Một trong các biến thể của sản phẩm sẽ được trang bị một lắp (lid) để bảo vệ các kỹ thuật thực hiện phân tích.**

Lắp sẽ che phần băng chuyền khi nó hoạt động. Lắp phải được khóa lại trước khi băng chuyền bắt đầu và không thể được mở ra trước khi băng chuyền dừng hoàn toàn. Hai cảm biến được thiết lập để phát hiện nếu lắp được đóng và nếu băng chuyền đang chuyển động. 
Khi mà lắp còn bị khóa thì có thể bắt đầu di chuyển băng chuyền về phí trước hoặc phía sau. Để thay đổi hướng cần phải dừng băng chuyền lại trước, tuy nhiên không cần thiết phải mởi lắp.
Bảng điều khiển gồm các nút sau:
- Khóa
- Mở 
- Tiến 
- Lùi
- Dừng
##Đặc tả thiết kế kiểm thử cho các phần PC của UV/TIT – 14 33a

###1.	Giới thiệu

**1.2.	Mục đích:**
Mục đích của phần đặc tả kiểm thử là để cung cấp một cái nhìn tổng quan về cái gì sẽ được kiểm thử khi kiểm thử hệ thống.

**1.3.	Tài liệu tham khảo:** 

| STT | Mô tả | ID |
| --------- | ---- | ------- |
|	[1] | Yêu cầu hệ thống, kiểm thử cơ bản | Requirements Specification for PC part of UV/TIT-14 33a.; Vers. 1.8 |

###2.	Bộ tính năng

Chương này sẽ mô tả về cấu trúc tổng quan về kiểm thử hệ thống của PCUV, trong đó, kiểm thử sẽ được chia nhỏ thành các bộ tính năng (Feature Sets) tổng quan.
Các thông tin sau được cung cấp cho mỗi bộ tính năng:

 - (nn): Một con số riêng biệt không thay đổi. Nó sẽ được sử dụng cho
   mục đích lần vết.
 - ns: Số hiệu mục, có thể dùng để tối ưu việc đọc tài liệu.
 - Mô tả: một đoạn mô tả ngắn về kiểm thử cái gì.
 - Cách tiếp cận: mô tả của kỹ thuật thiết kế kiểm thử được sử dụng
   trong việc thiết kế kiểm thử.
 - Khả năng lần vết: Nói đến các yêu cầu trong bộ tính năng. Khả năng
   lần vết sẽ bao gồm danh sách của các id riêng biệt yêu cầu tham khảo
   trong [1]

Phần kiểm thử này được chia ra thành các bộ tính năng như sau:
1. (FS1) Thiết lập hệ thống
2. (FS4) Hiệu chuẩn UV, IR và Buret
3. (FS2) Xác định các thành phần
4. (FS3) Mật độ của các thành phần (UV + sự kiểm soát của buret)
5. (FS6) Sự điều khiển của hệ thống băng chuyền

	**Bộ tính năng (FS1): Thiết lập hệ thống**

-	Mục tiêu: Để kiểm thử sự thiết lập của hệ thống, bao gồm vận chuyển thông tin và báo cáo về sự hiệu chuẩn
-	Độ ưu tiên: Trên trung bình
-	Cách tiếp cận: Kiểm thử cấu trúc của danh mục, kiểm thử yêu cầu đơn giản (Có/Không), các phương pháp phân vùng tương đương và phân tích giá trị biên
-	Khả năng lần vết: [22], [34], [35], [36], [37], ...
Bộ tính năng (FS2): Xác định các thành phần
-	Mục tiêu: Kiểm thử việc xác định và báo cáo của các thành phần.
-	Độ ưu tiên: Cao 
-	Cách tiếp cận: Kiểm thử yêu cầu đơn giản (Có/Không), phân vùng tương đương và phân tích giá trị biên, kiểm thử cú pháp và kiểm thử cây quyết định. 
-	Khả năng lần vết: [324], [325], [326], [339], [341],...
Bộ tính năng (FS3), Bộ tính năng (FS4), Bộ tính năng (FS5) : chưa hoàn tất
Bộ tính năng (FS6): Sự điều khiển của hệ thống băng chuyền
-	Mục tiêu: Để kiểm thử hệ thống băng chuyền, bao gồm, tốc độ, bắt đầu vào dừng đúng vị trí, sự hoạt động của lắp.
-	Độ ưu tiên: Dưới trung bình
-	Cách tiếp cận: ..., kiểm thử chuyển đổi trạng thái, ... 
-	Khả năng lần vết: [581] ...

###3.	Các điều kiện kiểm thử

Trong chương này, Các điều kiện kiểm thử cho mỗi bộ tính năng được diễn tả.

**3.3 Bộ tính năng (FS2): xác định các thành phần**

Bộ tính năng này bao gồm các yêu cầu liên quan đến việc xác định và báo cáo của các thành phần. Các tính năng thiết lập có một số điều kiện được bố trí trong tiểu mục tương ứng với các yêu cầu liên quan.

*3.3.7 Các điều kiện kiểm thử cho khoảng biên*

Các điều kiện kiểm thử cho khoảng biên có thể được biểu diễn bằng một cây phân loại đơn giản (tương tự như phân vùng tương đương) và phân tích giá trị biên liên quan. Tất cả những điều kiện kiểm thử này có thể được truy nguồn từ các yêu cầu tương tự, và chúng có cùng độ ưu tiên.
Các yêu cầu được bao phủ:


| Các yêu cầu được bao phủ: [324-NCS], [325-NCS]|| Ưu tiên: khoảng giữa ||
| --------- | ---- | ------- | ---------------- |
| | Nhập vào|  |  |
| (FS2).5.1 |  | <2 | Ngoài khoảng |
| (FS2).5.2 |  | 2 – 315 incl | Hợp lệ |
| (FS2).5.3 | 	| >315 | Ngoài khoảng |

*3.3.8 Các điều kiện kiểm thử cho phương pháp phân tích*
Các điều kiện kiểm thử cho việc xác định các phương pháp phân tích từ số mẫu có thể được thể hiện bằng cách sử dụng cây phân loại. Tất cả những điều kiện kiểm thử này có thể được truy nguồn từ các yêu cầu tương tự.

**3.5.  Bộ tính năng (FS6): kiểm soát các hệ thống băng tải**

Bộ tính năng này bao gồm các yêu cầu liên quan đến các hệ thống băng tải, bao gồm tốc độ, bắt đầu chính xác và vị trí dừng lại, thao tác đóng gói v.v… Các bộ tính năng có một số điều kiện được bố trí trong tiểu mục tương ứng với các yêu cầu liên quan.

*3.5.2 Các điều kiện kiểm thử cho thao tác đóng gói*

Các thao tác đóng gói có thể được minh họa trong sơ đồ máy trạng thái, nơi mà các trạng thái và các hiệu ứng được đánh số, và sự kiện “P” có thể được hiều như là sự ấn dấu.
 

| Các yêu cầu được bao phủ: [581]|Ưu tiên: khoảng giữa|
| --------- | ---------------- |
| Điều kiện kiểm thử |  |
| (FS6).11.1 | Thao tác đóng gói làm việc tùy theo sơ đồ máy trạng thái |
| (FS6).11.2 | Tất cả các quá trình chuyển dổi (không hiển thị) không hợp lệ là null-transitions |


#Phụ lục J: Đặc tả ca kiểm thử

Các mục kiểm thử bao phủ và các trường hợp kiểm thử cho một câu chuyện được tóm tắt trong các tiêu đề của trường hợp kiểm thử và ghi chú trên mặt sau của câu chuyện như sau:
+	Thư kí có thể tạo ra một loại hình đăng kí mới.
+	Thư kí có thể nhập tên, độ dài có sẵn, giá cả và cảm nhận cho một loại hình đăng kí mới.
+	Thư kí có thể nhìn thấy loại hình đăng kí đã tồn tại.
+	Thư kí có thể thay đổi tên, độ dài, giá cả cho một loại hình đăng kí đến chừng nào nó chưa có.
+	Thư kí có thể hủy các thay đổi của loại hình đăng kí trước khi nó được lưu trữ.
+	Thứ kí có thể lưu các thay đổi cho một loại hình đăng kí.

##Đặc tả ca kiểm thử cho máy tính của UV/TIT-14 33a

###1.	Giới thiệu

**1.2.	Mục đích**

Mục đích của phần này là liệt kê các trường hợp kiểm thử bắt nguồn từ các điều kiện kiểm thử.

**1.3.	Tài liệu tham khảo**

| Số tham chiếu | Mô tả | ID |
| --------- | ---------------- | ---------------- |
| [1] | Yêu cầu hệ thống và cơ sở kiểm thử| Requirements Specification for PC part of UV/TIT-14 33a.; Vers. 1.8 |
| [2] | Bộ tính năng và điều kiện kiểm thử |Test Design Specification for PC part of UV/TIT-14 33a.; Vers. 1.0 |



###2.	Các mục kiểm thử bao phủ

Phần này mô tả các mục bao phủ có thể bắt nguồn từ các điều kiện thử nghiệm được cung cấp trong [2]

**2.3. Bộ tính năng (FS2): Xác định các hợp chất**

Bộ tính năng này bao gồm các yêu cầu liên qua đến việc xác định và báo cáo các hợp chất. Bộ tính năng có một số hạng mục bao phủ có nguồn gốc từ điều kiện kiểm thử, chúng được sắp xếp trong các tiểu mục tương ứng với các yêu cầu liên quan.

*2.3.7. Mục bao phủ cho phạm vi đo lường*

Có 3 phân vùng tương đương hợp lệ và 6 ranh giới hợp lệ.

*2.3.8. Mục bao phủ cho phương pháp phân tích*

Các mục bao phủ là lá trong cây phân loại trong phần 3.3.8 trong [2]. Các tên miền con được in đậm. Có 10 lá có hiệu lực.

**2.5 Bộ tính năng (FS6): Điều khiển hệ thống băng chuyền**

*2.5.2. Mục bao phủ cho hoạt động mở nắp (Lid Operation)*

Để bao phủ Chow’s 0-switch của nhà máy trong FS6 .11.1 trong [2] có 6 sự biến chuyển sau đây: 
 
Các biến chuyển rỗng sẽ được xác định trong bản sau (in đậm):
 
###3.	Các ca kiểm thử

Phần này mô tả các trường hợp kiểm thử từ các mục kiểm thử bao phủ ở trên.

**3.3. Bộ tính năng (FS2): Xác định các hợp chất**

*3.3.7. Phạm vi đo lường*


| Test Case ID: 17-1   |	Mục đích: Kiểm tra phản ứng với mẫu giá trị nằm ngoài phạm vi |
| --------- | ---------------- |
| Điều kiện tiên quyết: | 	Thiết bị phải sẵn sàng cho lấy mẫu phân tích. Một mẫu NCS có giá trị là 1 phải được chuẩn bị.
|Đầu vào: 	|Thêm mẫu và bắt đầu phân tích
|Kết quả dự kiến: |	Màn hình hiển thị “mẫu không hợp lệ”

|Test Case ID: 17-4  | 	Mục đích: Kiểm tra phản ứng với mẫu giá trị nằm gần ranh giới của mẫu hợp lệ
| --------- | ---------------- |
| Điều kiện tiên quyết: 	| Thiết bị phải sẵn sàng cho lấy mẫu phân tích. Một mẫu NCS có giá trị là 315 phải được chuẩn bị.
| Đầu vào: 	| Thêm mẫu và bắt đầu phân tích
| Kết quả dự kiến: | 	Màn hình hiển thị “Cảnh báo”

3.3.8. Phương pháp phân tích

|  Test Case ID: 21-3 | 	Mục đích: Kiểm tra phân tích tự động của loại 1
| --------- | ---------------- |
| Điều kiện tiên quyết: | 	Cơ sở dữ liệu phải bao gồm: Một mẫu loại 1 với các bước thích hợp và một ID mẫu của 314.
| Đầu vào: | 	Nhập một mẫu với ID: A-1-314-221204
| Kết quả dự kiến: | 	Các phân tích phải được thực hiện mà không cần bất kì sự tương tác cần thiết nào.Một báo cáo được in ra , các bước liên quan đến mẫu loại 1 được thực thi. | 

| Test Case ID: 21-16  | 	Mục đích: Kiểm tra phân tích thủ công
| --------- | ---------------- |
| Điều kiện tiên quyết: 	| Form để nhập mẫu ID phải được lưu hành
| Đầu vào: 	| Nhập mẫu ID: M-2-518-240604
| Kết quả dự kiến: 	| Người dùng phải nhập từng bước như tiến trình phân tích. Người dùng được yêu cầu viết báo cáo. Báo cáo được in và những báo cáo này phải phản ánh những bước thực hiện.





