# Bài 4: Lưu trữ dữ liệu đơn giản với Docker Volume

## Các lệnh đã thực hiện

1. Tạo volume mới có tên là `easy-volume`:
```bash
docker volume create easy-volume
```

2. Dùng 1 container Alpine ghi nội dung vào volume:
```bash
docker run --rm -v easy-volume:/data alpine sh -c "echo 'Luu tru du lieu Docker' > /data/test.txt"
```

3. Dùng 1 container Alpine thứ hai đọc lại tệp đó:
```bash
docker run --rm -v easy-volume:/data alpine cat /data/test.txt
```

4. Kiểm tra danh sách volume trên máy:
```bash
docker volume ls
```

## Kết quả kiểm tra
Khi chạy lệnh đọc file, Terminal in ra đúng dòng chữ:
```
Luu tru du lieu Docker
```
<img width="1100" height="310" alt="ex4_ss09" src="https://github.com/user-attachments/assets/04520e9f-5a21-4eb6-9521-160228c6aa60" />

