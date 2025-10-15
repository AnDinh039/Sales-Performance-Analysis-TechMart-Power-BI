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
- **Định dạng:** File CSV
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
</table>

