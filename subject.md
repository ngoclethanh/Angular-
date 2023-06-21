# Day 1: SUBJECT
phương thức asObservable() được sử dụng chuyển đổi subject thành một observable.
Subject là một loại observable đặc biệt trong Angular, cho phép bạn cung cấp và nhận giá trị, cũng như thông báo cho các subscriber của nó. Tuy nhiên, có thể có trường hợp bạn muốn giới hạn quyền truy cập vào Subject chỉ dưới dạng một observable, mà không cho phép các thành phần khác thay đổi giá trị của nó.
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