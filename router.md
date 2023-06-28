# Day 3: Router
## Phương thức ForRoot và ForChild :
RouterModule mặc định cung cấp hai method là forRoot() và forChild(). Hai method này đều dùng để config routes, tuy nhiên:

1. forRoot được sử dụng để cấu hình router ở mức cao nhất trong ứng dụng, thường được gọi trong module gốc (root module) của ứng dụng.
 - Chỉ nên sử dụng một lần duy nhất trong toàn bộ ứng dụng.
 - Router được khai báo trong forRoot sẽ được chia sẻ và sử dụng trong toàn bộ ứng dụng.
 - forRoot cung cấp các cấu hình chung cho định tuyến như path, component, redirectTo, pathMatch, và các cấu hình khác.

2. forChild được sử dụng để cấu hình các định tuyến cho các module con (child module) trong ứng dụng.
 - Có thể sử dụng nhiều lần trong các module con khác nhau của ứng dụng.
 - Định tuyến được khai báo trong forChild chỉ có hiệu lực trong phạm vi module con đó và không được chia sẻ với các module khác.
 - forChild chỉ chứa các cấu hình đặc thù cho module con và không chứa các cấu hình chung của forRoot.
## pathMatch 
 Thuộc tính này xác định cách router sẽ xảy ra dựa trên URL được cung cấp.
 1. 'prefix': Đây là giá trị mặc định. Khi sử dụng 'prefix', router sẽ kiểm tra xem URL có khớp với đường dẫn cụ thể được chỉ định hay không. Nếu URL khớp với phần đầu của đường dẫn, định tuyến sẽ xảy ra. Điều này có nghĩa là URL có thể chứa các phần tử bổ sung sau đó và vẫn được coi là khớp.

 2. 'full': Khi sử dụng 'full', router sẽ yêu cầu URL khớp chính xác với đường dẫn được chỉ định. Điều này có nghĩa là URL không được phép chứa các phần tử bổ sung sau đó.

Ví dụ: Nếu bạn có một định tuyến với đường dẫn '/users', chỉ có URL '/users' mới khớp với định tuyến này. URL '/users/profile', '/users/settings', v.v. sẽ không khớp.
