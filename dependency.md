# Day 2: Dependency Injection
## Dependency Injection là gì ?
Trong Angular, Dependency Injection (DI) là một khía cạnh quan trọng trong việc xây dựng ứng dụng. 
## Method Injector là gì ?
Injector là một phần của hệ thống DI trong Angular, nó giúp quản lý việc cung cấp các dependencies (phụ thuộc) cho các thành phần của ứng dụng, như các service, các thành phần (components), hoặc các module.

## Medthod Get() ?
Sử dụng method get() của Injector để lấy một instance của dependency cụ thể. 
```typescript
const myServiceInstance = this.injector.get(myServiceToken);

```
Lưu ý rằng việc sử dụng method get() của Injector thường được áp dụng trong những trường hợp đặc biệt khi bạn không thể inject dependency trực tiếp thông qua constructor. Thông thường, DI qua constructor là phương pháp khuyến nghị để inject dependencies trong Angular