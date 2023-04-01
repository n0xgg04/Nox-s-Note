###Template trong CPP
> **Mục đích sử dụng** :  *Định nghĩa tổng quát cho hàm thay vì sử dụng overload để định nghĩa cho từng kiểu dữ liệu, từng class...*

- Ví dụ về mục đích sử dụng :
*Giả sử ta cần hàm tính tổng 2 số nhiều kiểu dữ liệu, thay vì ta viết hàm sum cho từng kiểu, thì ta chỉ cần viêt 1 hàm tổng quát duy nhất*

#####Ví dụ :
```cpp
int sum(int a , int b) //Hàm tính tổng cho 2 số nguyên
{
     return a+b;
}

float sum(float a , float b) //Hàm tính tổng cho 2 số thực
{
     return a+b;
}

```

*Việc viết nhiều hàm rất mất thời gian, vì vậy ta cần sử dụng template để viết hàm tổng quát duy nhất thay cho tất cả các hàm trên*

#####Cú pháp :
```cpp
template<class/typename X1, class/typename X2,...> 
//Sử dụng typename đối với kiểu dữ liệu... nhưng vẫn có thể dùng class cho kiểu dl nhé
```

*Viết lại hàm template cho hàm tính tổng trên ví dụ*

```cpp
template<class kieudl> //Dùng typename thay cho class cũng được
kieudl sum(kieudl x, kieudl y){
    return x+y;
}
```

*Với cách sử dụng trên, ta chỉ có thể tổng quát hoá các phần tử cùng kiểu dữ liệu*

> Giả sử : Cần tạo biên tính tổng 2 phần tử khác kiểu dữ liệu

- Ta không còn chỉ sử dụng 1 template để đặt kiểu dữ liệu tổng quát cho 2 biến truyền vào

- Solution :
```cpp

template<typename T1, typename T2> //tạo 2 tham số kiểu dữ liệu để lưu 2 kiểu dl khác nhau
auto sum(T1 a, T2 b) -> decltype(a + b) {
    return a + b;
}
```

*Đối với hai tham số khác kiểu dữ liệu, chúng ta sử dụng một hàm template với hai tham số kiểu dữ liệu và sử dụng **decltype** để xác định kiểu dữ liệu của kết quả.*