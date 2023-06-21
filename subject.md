# Day 1: SUBJECT

## Subject là gì ?

"Subject" là một loại Observable đặc biệt, nó vừa là 1 Observable (chúng ta có thể subscribe vào nó) ,vừa là 1 Observer (với đầy đủ các method để chúng ta tự control khi nào gửi notification), chỉ nhận data sau khi đã subscribe.

Subject có thể được sử dụng để chia sẻ dữ liệu giữa các Component trong Angular, ví dụ như giữa các Component con và cha, hoặc giữa các Component không có mối quan hệ trực tiếp. Khi có sự thay đổi trong dữ liệu, Subject sẽ thông báo đến các Component đã đăng ký và cung cấp giá trị mới cho chúng.

Có 2 loại Subject hay được sử dụng bao gồm:

1.BehaviorSubject: Subject này lưu trữ giá trị hiện tại và phát ra giá trị cuối cùng khi có một Component mới đăng ký. Component mới đăng ký sẽ nhận được giá trị hiện tại và các giá trị mới sau đó.

2.Subject: Subject cơ bản không lưu trữ giá trị trước đó. Nó chỉ phát ra các giá trị mới nhất cho tất cả các Component đã đăng ký.

phương thức asObservable() được sử dụng chuyển đổi subject thành một observable.
asObservable(): Phương thức này trả về một observable mới khi bạn subscribe vào nó

```typescript
import { Subject } from 'rxjs';

const mySubject = new Subject<number>();

const myObservable = mySubject.asObservable();

myObservable.subscribe(value => {
  console.log(`Received value: ${value}`);
});

mySubject.next(1); // Gửi giá trị 1 đến Subject

// Output: Received value: 1

mySubject.next(2); // Gửi giá trị 2 đến Subject

// Output: Received value: 2
```
Ở ví dụ trên, mySubject là một Subject và myObservable là một observable được tạo ra từ mySubject bằng cách sử dụng phương thức asObservable(). Khi chúng ta subscribe vào myObservable, chúng ta chỉ có thể nhận các giá trị mà mySubject gửi đi. Các giá trị mới không thể được gửi vào mySubject thông qua myObservable.