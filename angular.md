
# Day 4: Sự khác nhau giữa Observable và Promise    
## concept :
- Promise: Là một đối tượng biểu thị kết quả của một hoạt động không đồng bộ. Nó chỉ trả về một giá trị duy nhất, hoặc một lỗi nếu có.
- Observable: Là một chuỗi các giá trị được phát ra theo thời gian. Nó có thể trả về nhiều giá trị 
## activation :
- Promise: Một Promise khi được kích hoạt sẽ trả về kết quả duy nhất khi hoàn thành.
- Observable: Một Observable sẽ không được kích hoạt cho đến khi có một Subscriber đăng ký để theo dõi nó. Nó có thể được kích hoạt nhiều lần và phát giá trị trong suốt quá trình thực thi.

## Xử lý lỗi : 
- Promise: Sử dụng .catch() hoặc try/catch để xử lý lỗi.
- Observable: Sử dụng .catch() hoặc retry(), retryWhen() để xử lý lỗi và các toán tử xử lý lỗi khác.
Ví dụ: Nếu bạn có một định tuyến với đường dẫn '/users', chỉ có URL '/users' mới khớp với định tuyến này. URL '/users/profile', '/users/settings', v.v. sẽ không khớp.
## Sự linh hoạt :
- Promise: Thường được sử dụng cho các hoạt động không đồng bộ đơn giản và chỉ trả về một giá trị.
- Observable: Có thể xử lý các luồng dữ liệu phức tạp, sự kiện, và các tác vụ không đồng bộ phức tạp hơn. Nó cung cấp các toán tử mạnh mẽ để xử lý, lọc và biến đổi dữ liệu.

Khi sử dụng trong Angular, Observable thường được sử dụng rộng rãi hơn Promise, đặc biệt trong các tác vụ không đồng bộ phức tạp như giao tiếp với API hoặc xử lý các sự kiện người dùng.
Observable có thể chứa được nhiều giá trị trong nó, còn Promise thì không. Chúng ta hãy tưởng tượng Observable như một array, còn Promise giống như một single value. Điều đó khiến Observable linh động hơn trong việc lưu trữ dữ liệu so với Promise. Bên cạnh đó Observable cũng chính là một dòng chảy (stream), và dòng chảy này được thay đổi theo thời gian. Chúng ta có thể truyền bất cứ giá trị nào vào dòng chảy đó và ngay lập tức Observable sẽ emit cho chúng ta giá trị mới.