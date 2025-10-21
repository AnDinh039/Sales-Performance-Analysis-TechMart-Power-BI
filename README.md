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
- Tổng số đơn hàng là **20 đơn** thu về **27 triệu VND**, biên lợi nhuận gộp đạt **15.84%** với lợi nhuận là **4.28 triệu VND**. Trong đó, giá trị mỗi đơn hàng trị giá **1.353 triệu VND**. Tuy nhiên, **tỷ lệ đạt mục tiêu đề ra đang rất thấp**, các chỉ số như doanh thu và đơn hàng chỉ đạt **1.59%** và **1.34%**, thấp hơn nhiều so với kỳ vọng mặc dù tỷ lệ tỷ lệ AOV cao tới **118.64%**.
  
    → *Mặc dù **chiến lược upselling/cross-selling hiệu quả** nhưng **biên lợi nhuận vẫn ở mức 15.84%** cho thấy giá sản phẩm, các loại chi phí chưa cân đối. **Hiệu suất hoạt động chưa ổn định và cần cải thiện***
- Về khách hàng, tỷ lệ khách hàng **quay lại mua** thấp chỉ đạt **18.75%**, chủ yếu là khách hàng **mới** chiếm **81.25%**

  → *Điều này cho thấy **các sản phẩm và chiến dịch marketing** hiện tại có hiệu quả trong việc thu hút khách hàng mới, nhưng chưa đủ để giữ chân và duy trì tệp khách hàng hiện hữu.*
  
**2. Xu hướng doanh thu theo ngày**
- Doanh thu (từ ngày 15-24) trung bình đạt mức **2.7 triệu VND/ngày**. Trong đó, doanh thu đạt đỉnh vào ngày 22 **(4.2 triệu VND)** và chạm đáy vào 20 **(1.6 triệu VND)**, nhìn chung doanh thu có sự biến động rất lớn với chênh lệch đáng kể giữa đỉnh và đáy.
  
   → *Doanh thu có nhiều biến động, nhưng **đường xu hướng** cho thấy doanh thu có xu hướng **tăng trưởng** về lâu dài.*

**3. Doanh thu theo kênh bán hàng** 
- **Kênh Online** hoạt động hiểu quả với doanh thu đạt được là **10.3 triệu VND**, chiếm **38.03%**. Mặc dù số lượng đơn chỉ đứng thứ hai sau **kênh In-Store (7 đơn so với 8 đơn)** nhưng **giá trị trung bình mỗi đơn** đạt được là **1.47 triệu VND**, cao hơn nhiều so với 2 kênh còn lại.

  → ***Khách hàng có xu hướng chi tiêu nhiều hơn khi mua sắm trực tuyến**, có thể nhờ **các chiến dịch quảng cáo tốt và nhắm đúng** khách hàng nên nhận được sự **thu hút lớn từ khách hàng tiềm năng** và **tăng giá trị trung bình mỗi đơn**.*
  
**II. Channel Performance**
<img width="2000" height="1515" alt="image" src="https://github.com/user-attachments/assets/bf3380a7-07a4-4d41-b181-67709bf3300d" />
**<img width="32" height="32" alt="magnifying-glass" src="https://github.com/user-attachments/assets/9e563f9f-2125-4421-b48c-6a805dc8d6b9" />Phát hiện chính** 

**III. Store & Regional Performance**
<img width="2000" height="1447" alt="image" src="https://github.com/user-attachments/assets/7da8b7b0-d62d-46b4-a351-eb2a9e8aa3b4" />
**<img width="32" height="32" alt="magnifying-glass" src="https://github.com/user-attachments/assets/9e563f9f-2125-4421-b48c-6a805dc8d6b9" />Phát hiện chính** 

**IV. Product Intelligence**
<img width="2000" height="1515" alt="image" src="https://github.com/user-attachments/assets/a6a169f9-db92-4ebc-a2e0-210ed8e7232d" />
**<img width="32" height="32" alt="magnifying-glass" src="https://github.com/user-attachments/assets/9e563f9f-2125-4421-b48c-6a805dc8d6b9" />Phát hiện chính**  

**V. Customer Analytics**
<img width="2000" height="1515" alt="image" src="https://github.com/user-attachments/assets/89d9f6d3-5518-4a2c-ae99-51ead4322dc3" />
**<img width="32" height="32" alt="magnifying-glass" src="https://github.com/user-attachments/assets/9e563f9f-2125-4421-b48c-6a805dc8d6b9" />Phát hiện chính** 

**VI. Team & Employee Performance**
<img width="2000" height="1515" alt="image" src="https://github.com/user-attachments/assets/9ca840e9-16ac-44e5-bf80-0d19b6c3d04b" />
**<img width="32" height="32" alt="magnifying-glass" src="https://github.com/user-attachments/assets/9e563f9f-2125-4421-b48c-6a805dc8d6b9" />Phát hiện chính** 









