#Báo cáo bài tập tuần 7

##Mô tả bài toán
* Kiểm tra xem 1 chuỗi có thỏa mãn yêu cầu là 1 tên đăng nhập hay không?
* Tên đăng nhập là chuỗi thỏa mãn:
	* Có độ dài 4-16 kí tự chữ thường, hoa hoặc số
	* Kí tự bắt không được là số
	* Không chứa các kí tự đặc biệt

##Phương thức cần kiểm thử
```java
	public String test(String s){
			
		int index=1;
		int start = s.charAt(0);
		
		boolean DieuKien1=(s.length()>=4 && s.length()<=16);
		boolean DieuKien2=((start>=97 && start<=122) || (start>=65 && start<=90));
					
		if(DieuKien1 && DieuKien2){
			
			while(index < s.length()){
				
				int check = s.charAt(index);
				
				if((check>=48 && check<=57) || (check>=97 && check<=122) || (check>=65 && check<=90)){
					index++;
				} 
				else{
					break;
				}         
			}
		}
		
		if(index == s.length()){
			return "Ok! Ten dang nhap hop le";
		}else{
			return "Error! Ten dang nhap khong hop le";
		}	        
	}
```

##Đồ thị chu trình
![flow](https://github.com/ducanhk58uet/int3117-2016/blob/master/NguyenHuuTu/BT3/img/tuan%207.png?raw=true)

##Xác định du-pair cho từng biến
* Biến DieuKien1:

du-pair|path(s)
-------|-------|
2-4|2-3-4

* Biến DieuKien2:

du-pair|path(s)
-------|-------|
3-4|3-4

* Biến index:

du-pair|path(s)
-------|-------|
0-5|0-1-2-3-4-5-6-7-8-5-9
0-9|0-1-2-3-4-5-6-7-9
0-9|0-1-2-3-4-9
8-9|8-5-9
8-9|8-5-6-7-9

##Sinh test cases cho các biến

\#	|Tên biến|path(s)|Input Value of String s |Output |Expected |Result
----|--------|--------|-----------------------|-------|---------|------|
0.	|DieuKien1|2-3-4 |nguyen				  |Ok	  |Ok		|pass
1.	|DieuKien2|3-4   |n1g2u3y4				  |Ok	  |Ok		|pass	
2.	|index    |0-1-2-3-4-5-6-7-8-5-9 |nguyenhuutu				  |Ok	  |Ok		|pass
3.	|         |0-1-2-3-4-5-6-7-9 |n#guyen%huu@tu				  |Error	  |Error		|pass
4.	|         |0-1-2-3-4-9 |1nguyenhuutu				  |Error	  |Error		|pass

```java
	@Test
	public void test0() {
		String s= "nguyen";
		String expResult= "Ok! Ten dang nhap hop le";
		String result = name.test(s);
		assertTrue(expResult==result);
	}
	
	@Test
	public void test1() {
		String s= "n1g2u3y4";
		String expResult= "Ok! Ten dang nhap hop le";
		String result = name.test(s);
		assertTrue(expResult==result);
	}
	
	@Test
	public void test2() {
		String s= "nguyenhuutu";
		String expResult= "Ok! Ten dang nhap hop le";
		String result = name.test(s);
		assertTrue(expResult==result);
	}
	
	@Test
	public void test3() {
		String s= "n#guyen%huu@tu";
		String expResult= "Error! Ten dang nhap khong hop le";
		String result = name.test(s);
		assertTrue(expResult==result);
	}
	
	@Test
	public void test4() {
		String s= "1nguyenhuutu";
		String expResult= "Error! Ten dang nhap khong hop le";
		String result = name.test(s);
		assertTrue(expResult==result);
	}
```

##Độ bao phủ
![](https://github.com/ducanhk58uet/int3117-2016/blob/master/NguyenHuuTu/BT3/img/cover.PNG?raw=true)

##Nhận xét
* Chung:
	* Cả 2 đều hỗ trợ quá trình tạo test cases khá thuận lợi
	* Độ bao phủ của cả 2 đều tương tự nhau
	* Cả 2 đều chưa quét qua trường hợp boolean
* Ưu thế của MCDC:
	* Dùng MCDC sẽ kiểm soát được các câu lệnh điệu kiện tốt hơn
	* Quá trình sinh test cases sẽ quét hết trường hợp
* Ưu thế của All-du-Path:
	* Sinh test cases theo luồng đồ thị nên rành mạch và dễ dàng hơn
	* Có thể phủ qua một số trường hợp câu lệnh điều kiện trên đường đi qua của thị
	