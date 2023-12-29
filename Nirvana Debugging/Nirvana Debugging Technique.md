## Nirvana Debugging

### Table of Content
1. [Giới thiệu](#giới-thiệu)


### Giới thiệu <a name = "giới-thiệu"></a>
Tiếp nối bài viết trước đã tìm hiểu về sử dụng Direct Syscall (link bài viết: [Direct Syscall Blog](https://github.com/vuongle-vigo/WinMalHack-Blog/blob/main/Bypass%20AV%20Hook%20-%20Direct%20Syscall/Bypass%20AV%20Hooking%20with%20Direct%20Syscall.md)), lần này chúng ta sẽ tìm hiểu kỹ thuật Nirvana Debugging, hiểu 1 cách ngắn gọn kỹ thuật này vẫn sẽ cho chúng ta thông tin của API được gọi kể cả nó được gọi bằng phương pháp nào.
### Nirvana Debugging
Kỹ thuật sẽ đặt 1 hook sau khi syscall được thực hiện, tức là kết quả của API đã được trả về, lúc này ta sẽ phân tích kết quả trả về để xem thông tin của API đã được gọi.
![Flow call API and return callback](images\map.png)
</br>
Như chúng ta thấy, **my_callback_hooking_fn** sẽ được đặt ngay sau khi **syscall function** trả về.
