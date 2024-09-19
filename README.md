# ĐỒ ÁN CUỐI KHÓA - PHÂN TÍCH DỮ LIỆU

## 1- Xác định bài toán, các yêu cầu nghiệp vụ và các chỉ số cần báo cáo
### 1.1- Bài toán cần giải quyết:
Phân tích tình hình kinh doanh của quán cà phê, với mong muốn xác định hành vi tệp khách hàng và thói quen mua sắm của khách hàng.
Căn cứ hiện trạng bán hàng để hiệu quả kinh doanh để đưa ra các chiến lược kinh doanh, tiếp thị hiệu quả, thu hút thêm khách hàng và nâng cao sự hài lòng của khách hàng.
### 1.2- Yêu cầu nghiệp vụ:
- Phân tích hành vi, thói quen mua sắm của khách hàng. Nhận diện các nhóm đối tượng khách hàng.
- Đánh giá doanh thu và khả năng tiêu thụ của các loại sản phẩm.
- Căn cứ doanh số bán hàng, đưa ra các chiến lược kinh doanh và tiếp thị hiệu quả.
### 1.3- Chỉ số báo cáo:
- Doanh thu tổng, doanh thu theo từng sản phẩm, doanh thu theo khung giờ/ ngày, ...
- Số lượng sản phẩm bán ra, tỷ lệ tồn kho
- Giá trị hóa đơn trung bình, giá trị các dòng sản phẩm
- Phân khúc khách hàng, hành vi - thói quen mua sắm.
## 2- Thu thập dữ liệu
- `Coffee shop sample data` từ [Kaggle](https://www.kaggle.com/datasets/ylchang/coffee-shop-sample-data-1113/data)
  <br /> Hạn chế của bộ dữ liệu: Giới hạn về khoảng thời gian (chỉ trong 1 tháng).
  <br /> Thời gian giao dịch, `transaction_date` và `transaction_time` không hợp lý, cùng một ngày lại có vài trăm giao dịch mà chỉ cách nhau vài giây hoặc vài phút, của cùng một khách hàng `customer_id`
- `Coffee shop sales` từ [Kaggle](https://www.kaggle.com/datasets/ahmedabbas757/coffee-sales)
  <br /> Hạn chế của bộ dữ liệu: Giới hạn về số lượng bảng dữ liệu.
- `Coffee shop Sales/ Inventory/ Staff` từ [Kaggle](https://www.kaggle.com/datasets/viramatv/coffee-shop-data)
  <br /> Hạn chế của bộ dữ liệu: Giới hạn về khoảng thời gian và số lượng dòng.
## 3- Data Warehouse - ETL
- Mặt hạn chế của bộ dữ liệu: khoảng thời gian ngắn (chỉ 1 tháng)
  <br /> và không có mô tả các cột dữ liệu: không hiểu được cột `order_no` và `line_item_id` trong bảng `sales_receipts`
- Cập nhật bộ dữ liệu, đã tìm thấy trang download dữ liệu từ nguồn IBM: [link](https://accelerator.ca.analytics.ibm.com/bi/?perspective=authoring&pathRef=.public_folders%2FIBM%2BAccelerator%2BCatalog%2FContent%2FDAT00065&id=i7B18B79B67E44BBE94A115C21EDF4669&objRef=i7B18B79B67E44BBE94A115C21EDF4669&action=run&format=HTML&cmPropStr=%7B%22id%22%3A%22i7B18B79B67E44BBE94A115C21EDF4669%22%2C%22type%22%3A%22reportView%22%2C%22defaultName%22%3A%22DAT00065%22%2C%22permissions%22%3A%5B%22execute%22%2C%22read%22%2C%22traverse%22%5D%7D)
  <br /> có bổ sung thêm 1 tháng, và đổi tên cột dữ liệu `order` thành `order_no`
- Hướng xử lý: bỏ bớt các cột dữ liệu không nắm thông tin, thay đổi các chỉ số phân tích từ tháng thành ngày (churn rate)
