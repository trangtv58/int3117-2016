/* JUNIT TESTING: */


1. Giới thiệu:
Họ và Tên: Trinh Van Trang
MSSV: 13020453
Lớp : QHI-2013 K58CLC

2. Bài toán:
<ul><li>PhuongTrinhBac2.java: Giải phương trình bậc 2.</li>
<li>PhuongTrinhBac2Test: JUnit testing.</li></ul>

3. Mô tả 
 Áp dụng phuong pháp phân lớp tương đương đối với delta và phương pháp dùng bảng quyết định đối với hệ số a,b,c của phương trình bậc 2 
 Với 3 phân lớp: delta >0 và delta < 0 và delta =0
 Sử dụng phương pháp lập bảng quyết định cho giá trị của hệ số a,b,c 

| Cột 1 |  Cột 2 | Cột 3  | Cột 4   | Cột 5  | Cột 6   | Cột 7 |
|---|---|---|---|---|---|----|   
| a=0 | T  | F   | T  | T  | F  | T |
| b=0 | -  | F  | T  | F  |  T | T |
| c=0 |  F | T  | F  | T  |  T | T |
| vô nghiệm  |   |  x |   |   |   |  |
| vô số nghiệm |   |   |   |   |   | x|
| chưa xác định |   |   | x  | x  |   |  |
| có nghiệm duy nhất |  x |   |   |  | x  |  |

Từ bảng quyết định ta có 7 ca thử nghiệm cho các hệ số a,b,c
```@Test
	public void GiaiPTKhiTatCaHeSoBangKhong() {
		PhuongTrinhBac2 test = new PhuongTrinhBac2();
		String x = test.giaiPT(0, 0, 0); 
		assertEquals("Phuong trinh co vo so nghiem",x);
	}
	
	@Test
	public void GiaiPTKhiHeSo_B_KhacKhong() {
		PhuongTrinhBac2 test = new PhuongTrinhBac2();
		String x = test.giaiPT(0, 4, 0); 
		assertEquals("Phuong trinh co nghiem duy nhat "+0.0,x);
	}
	
	@Test
	public void GiaiPTKhiHeSo_C_KhacKhong(){
		PhuongTrinhBac2 test = new PhuongTrinhBac2();
		String x = test.giaiPT(0, 0, 4);
		assertEquals("Phuong trinh vo nghiem",x);			
	}
	
	@Test
	public void GiaiPTKhiHeSo_A_KhacKhong(){
		PhuongTrinhBac2 test = new PhuongTrinhBac2();
		String x = test.giaiPT(4, 0, 0);
		assertEquals("Phuong trinh co nghiem kep x1= x2= "+-0.0,x);			
	}
	
	@Test
	public void GiaiPTKhiHeSoThoaMan_Delta_LonHonKhong(){
		PhuongTrinhBac2 test = new PhuongTrinhBac2();
		String x = test.giaiPT(-1, 2, 3);
		assertEquals("X1= " +-1.0+ "X2= " +3.0,x);			
	}
 
 @Test
	public void GiaiPTKhiHeSo_a_BangKhong (){
		PhuongTrinhBac2 test = new PhuongTrinhBac2();
		String x = test.giaiPT(0, 2, 4);
		assertEquals("Phuong trinh co nghiem duy nhat "+-2.0 ,x);
	}
	
	@Test
	public void GiaiPTKhiHeSo_b_BangKhong(){
		PhuongTrinhBac2 test = new PhuongTrinhBac2();
		String x = test.giaiPT(2, 0, 4);
		assertEquals("Phuong trinh vo nghiem",x);
	}
 ```
	
