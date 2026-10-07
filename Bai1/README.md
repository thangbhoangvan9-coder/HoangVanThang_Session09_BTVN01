Dò vết & Sửa lỗi Truy cập Thuộc tính Động
1. Phân tích lỗi
Lỗi nằm ở dòng:
const basePrice = bookingReservation.priceKey;
priceKey là một biến có giá trị:
const priceKey = "roomPrice";
Khi sử dụng Dot Notation:
bookingReservation.priceKey
JavaScript sẽ tìm thuộc tính có tên chính xác là priceKey.
Trong object bookingReservation không có thuộc tính priceKey, chỉ có thuộc tính roomPrice.
Vì vậy:
bookingReservation.priceKey
trả về:
undefined
Sau đó phép tính:
undefined * 0.3
cho kết quả NaN, làm tổng tiền cũng trở thành NaN.
Cách sửa
Sử dụng Bracket Notation:
bookingReservation[priceKey]
Vì priceKey có giá trị "roomPrice" nên JavaScript sẽ tương đương với:
bookingReservation["roomPrice"]
và lấy được giá trị:
1500000

2. Test Cases
Trường hợp kiểm thử	Dữ liệu đầu vào	Kết quả sai thực tế	Kết quả đúng mong đợi
Nhận phòng trước 12h	roomPrice = 1500000, checkInHour = 9	basePrice = undefined, phụ thu = NaN, tổng tiền = NaN	Phụ thu = 450000, tổng tiền = 1950000
Kiểm tra truy cập giá phòng bằng biến động	priceKey = "roomPrice"	bookingReservation.priceKey trả về undefined	bookingReservation[priceKey] trả về 1500000

3. Kết luận
Dot Notation phù hợp khi biết trực tiếp tên thuộc tính:
bookingReservation.roomPrice
Bracket Notation được sử dụng khi tên thuộc tính nằm trong một biến:
const priceKey = "roomPrice";
bookingReservation[priceKey];
Trong bài này phải dùng Bracket Notation để lấy đúng giá phòng và tránh kết quả undefined và NaN