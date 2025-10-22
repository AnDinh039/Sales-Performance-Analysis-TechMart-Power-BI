# Sales Performance Analysis For The TechMart | Power BI
![](https://cdn.shopify.com/s/files/1/0070/7032/articles/sales-strategy_266f8be6-5f30-4aa1-8668-5d169ee705ba.jpg?v=1729110941)

**Tác giả:** Đinh Hữu An

**Ngày:** Oct 2025

**BI tool:** Power BI

## MỤC LỤC
### 1. Bối Cảnh Kinh Doanh 
### 2. Cấu Trúc Dữ Liệu
### 3. Luồng Tư Duy Thiết Kế
### 4. Key Insight & Trực Quan Hoá Dữ Liệu
### 5. Kết Luận & Hướng Giải Quyết
________________________________________________________________________________________________________________________________________________________
## 1. BỐI CẢNH KINH DOANH
### 1.1. Tổng Quan Công Ty
**TechMart Vietnam** là chuỗi bán lẻ điện tử với quy mô:
- <img src="https://cdn-icons-png.flaticon.com/512/869/869636.png" width="20"> **5 cửa hàng:** TP. Hồ Chí Minh (3), Hà Nội (1), Đà Nẵng (1)
- <img src="https://cdn-icons-png.flaticon.com/512/2331/2331970.png" width="20"> **3 kênh bán hàng:** Online, In Store, Mobile App
- <img src="https://cdn-icons-png.flaticon.com/512/1256/1256650.png" width="20"> **13 nhân viên bán hàng:** Associate (7), Senior (5), Junior (1)
- <img src="https://cdn3d.iconscout.com/3d/premium/thumb/product-3d-icon-png-download-4863042.png" width="20"> **20+ dòng sản phẩm:** Điện thoại, Laptop, TV, Gaming, Audio, Phụ kiện
  
**Doanh thu hiện tại**: Công ty đặt ra mục tiêu đạt doanh thu ~1.7 tỷ/tháng. Tuy nhiên trong tập dữ liệu này chỉ có dữ liệu bán hàng từ 15 tới 24/1/2025, vì vậy thực tế doanh thu hiện tại chỉ ~27.1 triệu trong vòng 10 ngày.

### 1.2. Vấn Đề Cần Giải Quyết
**1. Doanh thu & Tăng trưởng**
- Doanh thu đang tăng hay giảm
- Có đạt được mục tiêu đề ra không? Điểm uốn ở đâu?
- Kênh nào, cửa hàng nào đang thúc đẩy tăng trưởng?
  
**2. Lợi nhuận** 
- Lợi thuận thực tế sau khi trừ đi các loại chi phí là bao nhiêu?
- Kênh nào đạt lợi nhuận cao nhất?
- Cửa hàng nào đang thua lỗ?
  
**3. Tình trạng hoạt động**
- Hiệu suất của nhân viên như thế nào?
- Sản phẩm nào cần đẩy mạnh hoặc dừng?
- Hàng tồn kho có cân đối không?
  
**4. Khách hàng**
- Khách hàng nào mang lại giá trị lớn nhất?
- Tỷ lệ khách hàng quay lại mua như thế nào?
- Vùng/thành phố nào có tiềm năng phát triển?
  
**5. Chiến lược**
- Nên đầu tư thêm vào những mục nào?
- Cần đóng/mở cửa hàng nào?
### 1.3. Mục Tiêu Của Dự Án Phân Tích
**Xây dựng 6 dashboard để:**

- **Tổng quan:** Theo dõi các chỉ số tổng thể, nắm rõ tình hình để đưa ra quyết định chiến lược
- **Hoạt động:** Quản lý cửa hàng, kênh, nhóm mỗi ngày
- **Bán hàng:** Đánh giá hiệu suất cá nhân và nhóm
- **Marketing:** Đánh giá hành vi mua sắm và phân khúc khách hàng.
- **Sản phẩm:** Quản lý sản phẩm và kho

## 2. CẤU TRÚC DỮ LIỆU 
### 2.1. Tổng Quan Về Tập Dữ Liệu
- **Nguồn**: Nguyen Ngoc Tuan
- **Định dạng:** File Excel
- **Tập dữ liệu bao gồm 12 bảng chính**
### 2.2. Các Bảng Dữ Liệu Chính
<table>
  <tr>
    <td><strong>Bảng</strong></td>
    <td><strong>Số Dòng</strong</td>
    <td><strong>Mô Tả</strong></td>
  </tr>
  <tr>
    <td><strong>Orders</strong></td>
    <td>20</td>
    <td>Thông tin đơn hàng</td>
  </tr>
  <tr>
    <td><strong>Order_Items</strong></td>
    <td>44</td>
    <td>Chi tiết các sản phẩm có trong đơn hàng</td>
  </tr>
  <tr>
    <td><strong>Customers</strong></td>
    <td>16</td>
    <td>Thông tin khách hàng</td>
  </tr>
  <tr>
    <td><strong>Products</strong></td>
    <td>20</td>
    <td>Thông tin sản phẩm, danh mục</td>
  </tr>
  <tr>
    <td><strong>Stores</strong></td>
    <td>5</td>
    <td>Thông tin cửa hàng</td>
  </tr>
    <tr>
    <td><strong>Employees</strong></td>
    <td>13</td>
    <td>Thông tin nhân viên</td>
  </tr>
  <tr>
    <td><strong>Teams</strong></td>
    <td>5</td>
    <td>Cơ cấu tổ chức nhóm</td>
  </tr>
  <tr>
    <td><strong>Channels</strong></td>
    <td>3</td>
    <td>Chi phí và đặc điểm kênh</td>
  </tr>
    <tr>
    <td><strong>Store_Target</strong></td>
    <td>16</td>
    <td>KPI theo cửa hàng</td>
  </tr>
  <tr>
    <td><strong>Channel_Target</strong></td>
    <td>16</td>
    <td>KPI theo kênh</td>
  </tr>
  <tr>
    <td><strong>Team_Target</strong></td>
    <td>16</td>
    <td>KPI theo nhóm</td>
  </tr>
  <tr>
    <td><strong>Employee_Target</strong></td>
    <td>16</td>
    <td>KPI cá nhân</td>
  </tr>
</table>

### 2.3. Mối Quan Hệ Giữa Các Bảng
<table>
  <tr>
    <td><strong>Bảng</strong></td>
    <td><strong>Bảng Kết Nối</strong</td>
    <td><strong>Khoá</strong></td>
    <td><strong>Mối Quan Hệ</strong></td>
  </tr>
  <tr>
    <td><strong>Orders</strong></td>
    <td><strong>Customers</strong</td>
    <td>customer_id</td>
    <td>Nhiều - Một</td>
  </tr>
  <tr>
    <td><strong>Orders</strong></td>
    <td><strong>Stores</strong</td>
    <td>store_id</td>
    <td>Nhiều - Một</td>
  </tr>
    <tr>
    <td><strong>Orders</strong></td>
    <td><strong>Employees</strong</td>
    <td>employee_id</td>
    <td>Nhiều - Một</td>
      <tr>
    <td><strong>Orders</strong></td>
    <td><strong>Channel</strong</td>
    <td>channel_id</td>
    <td>Nhiều - Một</td>
  </tr>
    <tr>
    <td><strong>Order_Items</strong></td>
    <td><strong>Orders</strong</td>
    <td>order_id</td>
    <td>Một - Nhiều</td>
  </tr>
    <tr>
    <td><strong>Order_Items</strong></td>
    <td><strong>Products</strong</td>
    <td>product_id</td>
    <td>Một - Nhiều</td>
  </tr>
      <tr>
    <td><strong>Employees</strong></td>
    <td><strong>Teams</strong</td>
    <td>team_id</td>
    <td>Nhiều - Một</td>
  </tr>
        <tr>
    <td><strong>Employees</strong></td>
    <td><strong>Stores</strong</td>
    <td>store_id</td>
    <td>Nhiều - Một</td>
  </tr>
  <tr>
    <td><strong>Teams</strong</td>
    <td><strong>Stores</strong></td>
    <td>store_id</td>
    <td>Một - Một</td>
  </tr>
</table>

## 3. LUỒNG TƯ DUY THIẾT KẾ
### 3.1. <img width="32" height="32" alt="thought-leadership" src="https://github.com/user-attachments/assets/4d75784b-a264-402b-bb31-962826f64845" /> Thấu Hiểu 
<img width="1216" height="782" alt="image" src="https://github.com/user-attachments/assets/1e60b180-0a71-40c3-acf2-1ad8a4a53686" />

### 3.2. <img width="32" height="32" alt="customer-journey" src="https://github.com/user-attachments/assets/0119cff4-14d5-4a4d-b0c5-2e4cdd20559f" /> Hành Trình Của StakeHolders 
<img width="1216" height="782" alt="_Gradient Sale Promotional Business Flag (900 x 900 px) (1216 x 782 px)" src="https://github.com/user-attachments/assets/3fbc0123-d0a0-458b-a279-7d710384b04d" />

### 3.3  <img width="32" height="32" alt="idea" src="https://github.com/user-attachments/assets/4569a971-4186-4113-aa1a-717ea3f07c6b" /> Ý Tưởng
<img width="1216" height="782" alt="_Gradient Sale Promotional Business Flag (900 x 900 px) (1216 x 782 px) (1)" src="https://github.com/user-attachments/assets/cf3ea02e-36b2-4199-aaf8-5de493712bdc" />
<img width="1216" height="782" alt="_Gradient Sale Promotional Business Flag (900 x 900 px) (1216 x 782 px) (2)" src="https://github.com/user-attachments/assets/8d8a87e9-0ad4-4e0c-8552-3e9771df0df5" />
<img width="1216" height="782" alt="_Gradient Sale Promotional Business Flag (900 x 900 px) (1216 x 782 px) (3)" src="https://github.com/user-attachments/assets/6ba85859-76fa-4e29-9478-dd45ffed6de3" />
<img width="1040" height="478" alt="image" src="https://github.com/user-attachments/assets/aba2ad7d-6d6e-4511-a17f-ddf0b264fd53" />

### 3.4 <img width="32" height="32" alt="dashboard" src="https://github.com/user-attachments/assets/515157f3-7f5d-462a-b93b-06c58b161014" /> Xây Dựng Dashboard
**I. Executive Overview**
<img width="2000" height="1515" alt="image" src="https://github.com/user-attachments/assets/0dadfecb-2b79-4e41-8587-40cda286d889" />
**<img width="32" height="32" alt="magnifying-glass" src="https://github.com/user-attachments/assets/9e563f9f-2125-4421-b48c-6a805dc8d6b9" /> Phát hiện chính** 

**1. Về hiệu suất hoạt động**
- Tổng **20 đơn hàng** thu về **27 triệu VND**, **biên lợi nhuận gộp 15.84%** (lợi nhuận 4.28 triệu VND).
- **AOV đạt 1.35 triệu VND**, vượt 18.64% mục tiêu, nhưng **doanh thu và số đơn chỉ đạt lần lượt 1.59% và 1.34%** kế hoạch.
  
→ **Chiến lược upsell/cross-sell hiệu quả**, song chi phí vận hành và giá bán chưa cân đối, hiệu suất cần cải thiện.

- **Khách hàng mới chiếm 81.25%**, khách hàng quay lại chỉ 18.75%.
  
→ **Thu hút khách mới tốt**, nhưng **tỷ lệ giữ chân thấp**, cần tăng cường chăm sóc khách hàng hiện hữu.

**2. Xu hướng doanh thu theo ngày**
- Doanh thu trung bình 2.7 triệu VND/ngày, cao nhất ngày 22 (4.2 triệu) và thấp nhất ngày 20 (1.6 triệu).
  
→ **Doanh thu biến động mạnh**, nhưng xu hướng chung **đang tăng nhẹ** theo thời gian.

**3. Doanh thu theo kênh bán hàng** 
- **Kênh Online dẫn đầu (10.3 triệu VND, 38%)**, dù số đơn ít hơn **In-store (7 so với 8)**, nhưng **AOV cao nhất – 1.47 triệu VND**.
  
→ Khách hàng **chi tiêu nhiều hơn khi mua trực tuyến**, nhờ **chiến dịch quảng cáo** và **nhắm mục tiêu hiệu quả**.


**4. Đánh giá hiệu quả hoạt động của từng cửa hàng**
- **Flagship Store HCM đạt 10.3 triệu VND**, cao nhất hệ thống, dẫn đầu cả doanh thu và số đơn.
→ Cửa hàng này có **vị trí, quy mô và trải nghiệm khách hàng tốt**, tạo **lợi thế cạnh tranh rõ rệt**.
 

**5. Phân bố địa lý**
- **TP.HCM chiếm 48.31% doanh thu (13 triệu VND, 7 khách)**,
**Hà Nội** đạt **9.5** triệu VND nhưng có **CLV cao nhất – 8.55 triệu VND**.

→ **Hai thành phố lớn là thị trường trọng điểm**, đặc biệt **Hà Nội có khách hàng trung thành và chi tiêu cao hơn**, cần **tăng đầu tư marketing khu vực này**.
  
**II. Channel Performance**
<img width="2000" height="1515" alt="image" src="https://github.com/user-attachments/assets/9144f502-81f4-4ea7-b224-92dee8a31e68" />
**<img width="32" height="32" alt="magnifying-glass" src="https://github.com/user-attachments/assets/9e563f9f-2125-4421-b48c-6a805dc8d6b9" />Phát hiện chính** 

**1. Đánh giá hiệu suất các kênh**
- **Online (10.3M) và In-store (9.9M) đạt hiệu suất tốt**, duy trì **AOV > 1 triệu VND**, thể hiện **chiến lược marketing hiệu quả**.
**Mobile App** có **AOV cao (1.4M)** nhưng **doanh thu thấp (6.9M)**, cho thấy **tệp khách còn nhỏ và chưa ổn định**.
- Tỷ lệ chuyển đổi của cả ba kênh đang ở mức thấp **(< 20%)**
- Khách hàng có **thói quen mua sắm thường xuyên ở cửa hàng và trực tuyến**, hầu như ngày nào cũng có đơn

→ **Online & In-store nên tiếp tục được đẩy mạnh và cải thiện về các dịch vụ tư vấn hoặc khuyến mãi**, trong khi **Mobile App** cần đầu tư thêm về **trải nghiệm người dùng và nhận diện thương hiệu**.

**2. Tỷ suất hoàn vốn**
- Cả ba kênh đều đang có mức ROI âm, **Online - -76%**, **Mobile App - -59%**, trong đó **In-Store** đang ở mức báo động khi ROI chạm mức **-584%**
  
→ Cần xem lại các **chi phí vận hành, phần trăm hoa hồng, vv** ở các kênh trực tuyến, ứng dụng và **đặc biệt là các cửa hàng**

**3. Phương thức thanh toán**
- Phương thức thanh toán ở **cửa hàng đa số bằng tiền mặt (50%)**. Ở các nền tảng **trực tuyến và ứng dụng**, người dùng **chủ yếu sử dụng phương thức ví điện tử và thẻ**

→ Xu hướng thanh toán khác biệt rõ ràng ở trực tuyến và trực tiếp. **Tăng cường khuyến khích thanh toán điện tử** tại các cửa hàng để **đồng bộ trải nghiệm và giảm rủi ro xử lý tiền mặt**. 

**III. Store & Regional Performance**
<img width="2000" height="1447" alt="image" src="https://github.com/user-attachments/assets/006efc4f-118b-417e-afdb-347fdd2f1936" />
**<img width="32" height="32" alt="magnifying-glass" src="https://github.com/user-attachments/assets/9e563f9f-2125-4421-b48c-6a805dc8d6b9" />Phát hiện chính** 

**1. Cửa hàng hoạt động tốt nhất** 
- Cửa hàng **ST001 Flagship Store HCM** hiện đang dẫn đầu **doanh thu - 10.3 triệu VND**, số lượng đơn hàng là 7 và **AOV đạt hơn 117.66% (1.47 triệu VND)**
  
→ Tiếp tục **đẩy mạnh và nâng cao trải nghiệm người dùng**, xây dựng các **chiến lược marketing** hoặc các **sự kiện độc quyền tại chi nhánh** để thu hút thêm nhiều **tệp khách hàng cao cấp**

**2. Hiệu suất cửa hàng**
- Các cửa hàng **Da Nang Central (6 triệu VND)** và **District 7 Store (4 triệu VND)** xếp tiếp theo, chứng minh hiệu suất ổn định ở nhóm **cửa hàng chuẩn (Standard)**.
**Hanoi Premium (3 triệu VND)** và **Binh Thanh Outlet (3 triệu VND)** có doanh thu thấp hơn, biên lợi nhuận gộp lần lượt **780.000 – 695.000 VND**, cho thấy tiềm năng cải thiện về chi phí và sản phẩm trưng bày.
  
→ **Thành phố Hồ Chí Minh là cửa hàng chủ lực**, trong khi **Hà Nội và Đà Nẵng** cần tăng lưu lượng khách và cải thiện tỷ suất lợi nhuận.

**3. Phân tích lợi nhuận & chi phí**
- Tất cả các cửa hàng đều **chưa đạt điểm hòa vốn**, do **chi phí vận hành cao**. Mặc dù **ST001 Flagship Store HCM** tạo doanh thu cao nhất, lợi nhuận ròng âm do tổng chi phí vượt xa doanh thu.
  
→ Cần **tối ưu chi phí vận hành**, đặc biệt tại các cửa hàng lớn để cải thiện ROI.

**4. Phân tích theo khu vực**
- Khu vực Miền Nam đang chiếm tỷ trọng doanh thu cao nhất **(65%)**
- **Miền Trung (22.4%) và Miền Bắc (12.6%)** chỉ chiếm tỷ trọng trung bình và thấp tuy nhiên khu vực Miền Trung có AOV (1.4 triệu VND) cao hơn 2 khu vực còn lại.
- Danh mục sản phẩm nổi bật nhất chủ yếu là **Accessories**

→ **Miền Nam** là **thị trường trọng điểm**, đóng góp phần lớn doanh thu và số khách hàng (10/16). **Miền Bắc** tuy doanh thu thấp nhưng **khách có xu hướng chi tiêu cao hơn (CLV lớn)**, nên tập trung mở rộng nhóm **khách hàng cao cấp tại Hà Nội**. **Miền Trung có AOV cao nhất (1.5M)**, thể hiện **tiềm năng phát triển sản phẩm công nghệ cao như Gaming**.

**IV. Product Intelligence**
<img width="2000" height="1515" alt="image" src="https://github.com/user-attachments/assets/a6a169f9-db92-4ebc-a2e0-210ed8e7232d" />
**<img width="32" height="32" alt="magnifying-glass" src="https://github.com/user-attachments/assets/9e563f9f-2125-4421-b48c-6a805dc8d6b9" />Phát hiện chính**  
**1. Sản phẩm & thương hiệu nổi bật**
- **PROD003 (Smart TV 55")** là sản phẩm có **doanh thu cao nhất (6 triệu VND).**
- Thương hiệu **TechBrand** dẫn đầu về **số lượng bán ra (25 sản phẩm).**
→ Đây là hai **yếu tố chủ lực** giúp duy trì doanh thu ổn định toàn hệ thống.

**2. Các sản phẩm bán chạy nhất** 
- Chủ yếu là các sản phẩm **phụ kiện điện tử, thiết bị máy tính**. Tất cả đều ở trạng thái khoẻ, cho thấy nguồn hàng **ổn định và biên lợi nhuận tốt**.
→ **Nhóm sản phẩm phụ kiện nhỏ (chuột, pin sạc, tai nghe)** có sức mua mạnh – thích hợp để đẩy mạnh **chiến lược cross-sell**.

**3. Hiệu suất theo danh mục sản phẩm**
- **Televisions (19.7%)** và **Accessories (18.1%)** chiếm gần **40% tổng doanh thu**.
- **Accessories** có **biên lợi nhuận cao nhất (44.97%)**, tiếp theo là **Audio (38.64%)** và **Displays (36.36%).**
  
→ Đây là **3 nhóm ngành** mang lại **lợi nhuận cao nhất**, nên được **ưu tiên đầu tư, quảng bá và mở rộng danh mục.**

- **Smart Home** và **Wearables** có **doanh thu thấp (<1%)**
→ cần xem xét chiến lược định vị lại hoặc dừng đầu tư.

**4. Hiệu suất sản phẩm theo ma trận BCG**
- Nhóm **Star** gồm các sản phẩm có doanh thu cao và biên lợi nhuận tốt – cần tiếp tục duy trì đầu tư.
- Nhóm **Question Mark** có doanh số chưa ổn định – có thể thử nghiệm thêm khuyến mãi hoặc quảng cáo.
- Nhóm **Cash Cow** tạo lợi nhuận ổn định nhưng tăng trưởng thấp – nên tập trung duy trì.
- Nhóm **Dog** chiếm tỷ trọng nhỏ, cần xem xét loại bỏ để tối ưu tồn kho.

**5. Tình trạng tồn kho**
- **PROD004** và **PROD018** có **hàng tồn cao (200–500 đơn vị)**

→ rủi ro tồn kho lớn, cần đẩy mạnh khuyến mãi hoặc gộp combo.

- **PROD003 (Smart TV)** có mức **tồn hợp lý (90 đơn, 45 ngày cung ứng)**

→ Nhìn chung, kho hàng ở trạng thái ổn định, chỉ cần giảm hàng tồn dài hạn ở nhóm sản phẩm chậm luân chuyển.

**6. Phân tích bán kèm (Cross-Selling)**
- Dữ liệu cho thấy các sản phẩm thường được mua cùng **nhóm công nghệ nhỏ (PROD002, PROD008, PROD011, PROD014).**
  
→ Có thể thiết kế **combo ưu đãi khi mua kèm các sản phẩm khác** gồm chuột, tai nghe, sạc dự phòng… để **tăng AOV và doanh thu tổng**.

**V. Customer Analytics**
<img width="2000" height="1515" alt="image" src="https://github.com/user-attachments/assets/89d9f6d3-5518-4a2c-ae99-51ead4322dc3" />
**<img width="32" height="32" alt="magnifying-glass" src="https://github.com/user-attachments/assets/9e563f9f-2125-4421-b48c-6a805dc8d6b9" />Phát hiện chính** 
**1. Phân khúc khách hàng**
- Có 4 nhóm khách hàng. **Regular (6 khách - 37%), Premium (5 khách - 31%), New (3 khách - 19%) và VIP (2 khách - 13%)**
-> Khách hàng cao cấp bao gồm nhóm khách hàng **VIP và Premium** chiếm **44%** nhưng tạo ra hơn **75%** tổng giá trị vòng đời (CLV). Đây là nhóm mang lại **lợi nhuận chính**

**2. Giá trị vòng đời khách hàng (CLV)**
- Phân khúc khách hàng **VIP** có mức CLV trung bình cao hơn hẳn so với các phân khúc còn lại **(18.16 triệu VND)**, đơn hàng trung bình là **31.5 đơn** và AOV **2 triệu VND**
- Phân khúc **Premium** có mức CLV kém hơn VIP nhưng nhìn chung vẫn cao hơn 2 phân khác còn lại **(8.15 triệu VND)**, đây là phân khúc có tổng CLV cao nhất **(40.8 triệu VND)** và AOV ngang với VIP.

→ Khách **VIP** chi tiêu gấp ~5 lần **Regular**, có tần suất mua cao nhất (31 đơn). **Premium** có giá trị CLV ổn định, thể hiện nhóm khách hàng tiềm năng cần chăm sóc để nâng cấp lên VIP.

**3. Top 10 khách hàng giá trị nhất**
- **Le Van C (Hà Nội)** và **Dang Van G (TP.HCM)** – đều là **VIP**, có **CLV cao nhất hệ thống (~18 triệu VND mỗi người)**.
- Khách **Premium** tại **Thành phố Hồ Chí Minh (Nguyen Van A, Hoang Van E)** cũng có CLV cao **8–9 triệu VND**, cho thấy thị trường Miền Nam tập trung nhiều khách hàng trung thành.
  
→ **Hai thành phố lớn chiếm toàn bộ top 10 khách hàng**, khẳng định đây là **thị trường trọng tâm cần ưu tiên chăm sóc cá nhân hóa.**

**4. Điểm RFM (Recency – Frequency – Monetary)**
- Có 2 khách hàng **Champions (CUST001 & CUST016)**: mua thường xuyên, chi tiêu cao
  
→ cần duy trì đặc quyền và ưu đãi riêng.

- 5 khách hàng **Loyal**, 4 khách hàng **Potential Loyalist**, và 1 khách **At Risk (CUST003).**
  
→ Cần triển khai chương trình chăm sóc khách hàng theo cấp độ, đặc biệt là chiến dịch chào mừng trờ lại cho nhóm có dấu hiệu rời bỏ.

**5. Hành vi mua hàng đa kênh**
- Phân khúc khách hàng **VIP**	chủ yếu mua sắp qua các **nền tảng trực tuyến và ứng dụng Online (1) & Mobile App (2)**
  
→ Cho thấy họ ưa mua sắm trực tuyến, dễ tiếp cận qua quảng cáo digital.

- Phân khúc khách hàng **Premium** đa số mua qua **Online (4) & In-store (1)**
  
→ Mua nhiều qua web/app, song vẫn có trải nghiệm tại cửa hàng.

- Phân khúc khách hàng **Regular** **In-store (6)**
  
→ Thích trải nghiệm thực tế sản phẩm.

- Phân khúc khách hàng **New**	**Mobile App (2) & Online (1)**
  
→Thường bị thu hút bởi khuyến mãi hoặc chiến dịch digital.

**6. Phương thức thanh toán & sản phẩm yêu thích**

- Phân khúc khách hàng **VIP** khách hàng tại **Hà Nội và TP. Hồ Chí Minh** đều ưu tiên thanh toán bằng **thẻ hoặc ví điện tử.**
- Sản phẩm được nhóm này mua nhiều: **Smart TV 55”, Gaming Console Z, Portable SSD 1TB**

→ Nhóm sản phẩm giá trị cao, gắn với khách hàng VIP.

**VI. Team & Employee Performance**
<img width="2000" height="1515" alt="image" src="https://github.com/user-attachments/assets/9ca840e9-16ac-44e5-bf80-0d19b6c3d04b" />
**<img width="32" height="32" alt="magnifying-glass" src="https://github.com/user-attachments/assets/9e563f9f-2125-4421-b48c-6a805dc8d6b9" />Phát hiện chính** 

**1. Nhóm có hiệu suất tốt nhất**
- **TEAM01** dẫn đầu hệ thống với doanh thu **10.3 triệu VND**, gấp gần 1.7 lần **TEAM03 (6.1 triệu VND)**.
- Doanh thu trung bình trên mỗi thành viên của **TEAM01** đạt **2.6 triệu VND**, cao nhất toàn hệ thống.
  
→ **TEAM01** là đội nhóm **chủ lực**, có khả năng bán hàng và chuyển đổi vượt trội — **nên được xem là mô hình mẫu để nhân rộng.**

**2. Hiệu suất cá nhân**
- **EMP009 & EMP002** là hai nhân viên có **doanh thu cao nhất**, còn **EMP001 & EMP010** nổi bật về **hiệu suất và đánh giá xuất sắc.**
  
→ Cho thấy hiệu quả làm việc cá nhân không chỉ đến từ doanh thu mà còn từ **chất lượng phục vụ và khả năng giữ chân khách hàng.**

**3. Phân tích mục tiêu & tiến độ**
- Đa số nhân viên đều chưa đạt mục tiêu.
  
→ Hiệu suất chung của đội ngũ ổn định, cần hỗ trợ hoặc đánh giá lại mục tiêu cá nhân.

**4. 



