###LAMDBA FUNCTION<!-- slide -->
> Sử dụng để tạo **comparation** trong hàm sort

- Cách viết :
```cpp
 [](argv,argv){

 }
```
***nếu cần sử dụng biến bên ngoài ( global var)***
```cpp
 [&](argv1,argv2){

}
```

Ví dụ : Bài toán sắp xếp mảng theo số lần xuất hiện, số xuất hiện nhiều in trước, nếu cùng số lần xuất hiện thì sắp xếp theo giá trị

#####Ý tưởng :
1. Tạo mảng lưu số lần xuất hiện
2. Sử dụng hàm sort và viết lambda cmp function để sắp xếp theo ý muốn

#####Code :
<font size="2" color="red">Ở đây sử dụng [&] vì cần truy cập tới mảng cnt ở bên ngoài</font>
<font size="2">Vector a chứa các giá trị của mảng input của đề bài...</font>
```cpp
sort(a.begin(),a.end(),[&](int x,int y){ 
    if(cnt[x]!=cnt[y]) return cnt[x]>cnt[y]; //xếp theo số lần xuất hiện
    return x<y; //Nếu số lần xuất hiện bằng nhau thì xếp theo giá trị
});
```


