# Nhóm 4

- Lương Văn Chinh
- Phùng Khắc Khánh
- Nguyễn Ngọc Tú
- Nguyễn Văn Tuệ

[CSS Coding Standards](https://make.wordpress.org/core/handbook/best-practices/coding-standards/css/)

#CSS Coding Standards

Giống như các tiêu chuẩn viết code khác, mục đích của tiêu chuẩn viết css trong WordPress là tạo ra cơ sở cho sự phối hợp và nhận xét các khía cạnh khác nhau của dự án mã nguồn mở WordPress từ mã code đến theme và plugin. Trên hết là tạo ra được các đoạn code có thể đọc được, nhất quán và đẹp.

## Structure 

Có rất nhiều cách để kết cấu một stylesheet. Với css thì điều quan trọng là đảm bảo được tính đễ đọc. Điều này cho phép những người khác tham gia vào dự án có thể dễ dàng đọc hiểu các dòng chảy trong tài liệu.

-	Sử dụng tabs, khoảng cách để lùi đầu dòng các thuộc tính.
-	2 phần khác nhau nên được ngăn cách bằng 2 dòng trống, và giữa các khối trong một phần được ngăn bởi 1 dòng.
-	Mỗi selector nên được để trên một dòng riêng và kết thúc là dấu phảy hoặc cặp dấu ngoặc nhọn. Cặp thuộc tính, giá trị nên được đặt trên một dòng riêng lùi đầu dòng 1 tab và kết thúc bằng dấu chấm phảy. Ngoặc đóng nên được đặt bên trái với mức độ lùi đầu dòng như selector.

Chính xác:
```css
#selector-1,
#selector-2,
#selector-3 {
    background: #fff;
    color: #000;
}
```
Không chính xác:
```css
#selector-1, #selector-2, #selector-3 {
    background: #fff;
    color: #000;
    }
 
#selector-1 { background: #fff; color: #000; }
```

## Selectors

Đi kèm với việc chi tiết đòi hỏi một trách nhiệm lớn. Selector lỏng lẻo cho phép chúng ta đạt được hiệu quả, tuy nhiên nó có thể đem lại hậu quả xấu nếu không được kiểm tra trước. Selector theo vị trí cụ thể có thể tiết kiệm thời gian cho chúng ta, nhưng sẽ rất nhanh làm xáo trộn stylesheet.
Hãy sử dụng nhận định tốt nhất của bản thân để tạo ra một selector có thể cân bằng giữa style chung và các lớp DOM.

- Tương tự như Chuẩn WordPress PHP Coding Standards cho tên tập tin, sử dụng các ký tự in thường và các từ tách biệt bởi ký tự gạch ngang khi đặt tên selector. Tránh sử dụng CamelCase( viết hoa chữ cái đầu) hay phân tách các từ bởi ký tự gạch dưới.
- Sử dụng các selector có thể đọc hiểu được để mô tả element nào mà nó style.
- Selector thuộc tính nên sử dụng cặp dấu nhánh kép quanh giá trị.
- Ngừng sử dụng những thứ dư thừa, div.container có thể đơn giản thành .container.

Chính xác:
```css
#comment-form {
    margin: 1em 0;
}
 
input[type="text"] {
    line-height: 1.1;
}
```
Không chính xác:
```css
#commentForm { /* Tránh sử dụng camelcase. */
    margin: 0;
}
 
#comment_form { /* Tránh sử dụng gạch dưới.*/
    margin: 0;
}
 
div#comment_form { /* Tránh các dư thừa. */
    margin: 0;
}
 
#c1-xr { /* c1-xr là gì?! Sử dụng một cái tên tốt hơn. */
    margin: 0;
}
 
input[type=text] { /* Nên sử dụng [type="text"] */
    line-height: 110%
}
```

## Properties

Tương tự như selector, thuộc tính quá chi tiết sẽ cản trở tính linh hoạt của thiết kế. Càng ít chi tiết càng tốt. Chắc chắn rẳng bạn không lặp lại style hay dẫn đến một phương pháp cứng (khi các giải pháp linh hoạt là có thể chấp nhận hơn).

- Thuộc tính nên theo sau bởi một ký tự hai chấm và một ký tự khoảng trống.
- Tất cả các thuộc tính và giá trị nên sử dụng các ký tự in thường, trừ tên font và các thuộc tính với chi tiết của nhà cung cấp.
- Sử dụng mã hex cho màu sắc, hoặc rgba() nếu cần sử dụng opacity. Tránh sử dụng RGB và các ký tự in hoa, rút ngắn các giá trị khi có thể như: #fff thay vì #FFFFFF
- Sử dụng viết tắt (trừ khi override style) cho background, boder, font, list-style, margin và padding tối đa có thể. (xem thêm về [CSS Shorthand](https://codex.wordpress.org/CSS_Shorthand).)

Chính xác:
```css
#selector-1 {
    background: #fff;
    display: block;
    margin: 0;
    margin-left: 20px;
}
```
Không chính xác:
```css
#selector-1 {
    background:#FFFFFF;
    display: BLOCK;
    margin-left: 20PX;
    margin: 0;
}
```

## Property overiding

Có nghĩa là nhóm những thuộc tính giống nhau lại, đặc biệt là khi bạn có nhiều thuộc tính giống nhau.
Trên hết, chọn cái gì đó có nghĩa đối với bạn và có ngữ nghĩa theo một cách nào đó. Random overiding thì hỗn loạn và không có nghĩa. Trong Wordpress Core, lựa chọn của chúng tôi là hợp lý hoặc đã nhóm lại việc ghi đè, nơi các thuộc tính được nhóm lại theo thuộc tính và thứ tự của chúng trong group. Những thuộc tính trong group được sắp xếp chiến lược để tạo ra những biến chuyển giữa các phần, đặc biệt là chuyển đổi màu của background. Cơ sở cho việc ghi đè là:

- Display
- Positioning
- Box model
- Color and Typography
- Other

Những thứ chưa được sử dụng trong core, ví dụ như CSS3 animations, có thể không có một quy định như trên nhưng tương tự sẽ phù hợp trong một cách thức hợp lý. Chỉ là CSS đang phát triển, nên chúng tôi sẽ phát triển theo nó.

Top/Right/Bottom/Left là thứ tự sắp xếp giá trị trong các thuộc tính liên quan như padding, margin. Các định dạng cho góc nên là top-right, top-left, bottom-right, bottom-left. Điều này bắt nguồn từ cách viết tắt của các giá trị bắt buộc.

Ví dụ: 
```css
#overlay {
    position: absolute;
    z-index: 1;
    padding: 10px;
    background: #fff;
    color: #777;
}
```
Một phương thức khác thường được sử dụng, bao gồm cả Automattic/Wordpress.com Themes Team, thuộc tính được sắp xếp theo chữ cái, với hoặc không với một số ngoại lệ nhất định.

```css
#overlay {
    background: #fff;
    color: #777;
    padding: 10px;
    position: absolute;
    z-index: 1;
}
```
## Vendor prefixes 

Chúng tôi dùng Autoprefixer như là một pre-commit tool để dễ dàng quản lý những tiếp ngữ trình duyệt. Điều quan tâm của chúng trong việc theo dõi đầu ra không sử dụng Grunt, vendor prefixe có thể sẽ dài nhất (-webkit-) đến ngắn nhất (unprefixed). Tất cả những khoảng trống khác vẫn theo tiêu chuẩn.

Ví dụ:
```css
.sample-output {
    -webkit-box-shadow: inset 0 0 1px 1px #eee;
    -moz-box-shadow: inset 0 0 1px 1px #eee;
    box-shadow: inset 0 0 1px 1px #eee;
}
```
## Values 

Có rất nhiều cách để đặt giá trị cho thuộc tính. Hãy thực hiện theo các hướng dẫn sau để có được sự nhất quán.

-	Có khoảng cách trước giá trị và đặt sau dấu hai chấm.
-	Không có khoảng cách ở giữa các dấu ngoặc.
-	Luôn kết thúc bằng dấu chấm phẩy.
-	Sử dụng dấu ngoặc kép thay vì dấu ngoặc đơn, và chỉ dùng khi cần thiết như tên font có chứa khoảng cách.
-	Font weights nên được xác định bằng các giá trị số ( ví dụ nên dùng 400 thay vì dùng normal).
-	Giá trị 0 không cần phải có đơn vị trừ khi cần thiết ví dụ như transittion-duration.
-	Line height cũng hạn chế dùng đơn vị trừ các trường hợp cần thiết phải dùng các đơn vị cụ thể như px. Điều này thiên về quy ước phong cách hơn nhưng cũng có vấn đề đáng nói: 
[Unitless line heights](http://meyerweb.com/eric/thoughts/2006/02/08/unitless-line-heights/).)
-	Sử dụng một số 0 hàng đơn vị cho số thập phân kể cả trong rgba().
-	Các giá trị của một thuộc tính nên được phân cách bằng dấu phảy và một khoảng cách hoặc xuống dòng. Xuống dòng nên được sử dụng cho các giá trị có nhiều phần dài như box-shadow, text-shadow. Mỗi giá trị đầu tiên tại dòng mới phải thụt vào với mức độ như selector và cách lề trái cùng với giá trị trước.

Chính xác:
```css
.class { /* sử dụng đúng dấu ngoặc kép */
    background-image: url(images/bg.png);
    font-family: "Helvetica Neue", sans-serif;
    font-weight: 700;
}
 
.class { /* Sử dụng đúng sô 0 */
    font-family: Georgia, serif;
    text-shadow: 0 -1px 0 rgba(0, 0, 0, 0.5),
                       0 1px 0 #fff;
}
```
Không chính xác:
```css
.class { /* thiếu khoảng cách và dấu chấm phảy */
    background:#fff
}
 
.class { /* Có đơn vị ở giá trị 0 */
    margin: 0px 0px 20px 0px;
}
 
.class {
    font-family: Times New Roman, serif; /* Thiếu dấu ngoặc kép ở font */
    font-weight: bold; /* sử dụng tên cho font-weight */
}
```
##Media Queries

Media Queries cho phép chúng ta điều chỉnh DOM cho các kích thước màn hình khác nhau. Nếu bạn thêm một Media Queries hãy chắc chắn bạn đã kiểm tra cận trên và cận dưới.

-	Media Queries nên được đặt dưới cùng của các stylesheet.
-	Bộ quy tắc của Media Queries cũng nên thụt vào đầu dòng.

Ví dụ:
```css
@media all and (max-width: 699px) and (min-width: 520px) {
 
        /* Your selectors */
}
```
##Commenting 

-	Các bình luận dài nên được chia thành các dòng khoảng 80 ký tự.
-	Nên sử dụng các chỉ số (1.0, 1.1, 2.0 …) hỗ trợ cho việc tìm kiếm và nhảy đến vị trí mong muốn.
-	Tiêu đề của các mục hoặc các tiểu mục nên có một dòng mới ở trước và sau. Trong một comment không nên có dòng trống để tách các chú thích từ các mục liên quan.

Ví dụ: 
Trong một mục hoặc tiểu mục:

```css
/**
* #.# Section title
*
* Description of section, whether or not it has media queries, etc.
*/
 
.selector {
    float: left;
}
```
Trong 1 dòng: 

```css
/* This is a comment about this selector */
.another-selector {
    position: absolute;
    top: 0 !important; /* I should explain why this is so !important */
}
```
## Best Practices 

Viết code thông minh từ đầu sẽ giúp bạn có cái nhìn tổng quan và dễ dàng sửa đổi.

-	Nếu muốn sửa chữa 1 vấn đề nên xóa bỏ đoạn code trước khi bổ sung thêm.
-	Không nên sử dụng các Magic Numbers. Những con số này thường được sử dụng để sửa lỗi nhanh trong một trường hợp cụ thể.
-	Không xác định các thuộc tính và giá trị đã có sẵn ( ví dụ: display: block; trên những thẻ block)

