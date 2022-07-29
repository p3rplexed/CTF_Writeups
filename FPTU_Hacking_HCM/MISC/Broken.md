Broken
Chúng ta có 1 file ảnh PNG không thể mớ được Sau khi dùng “exiftool” và hex “editer” để chắc chắn nó là 1 file PNG và nó đã bị sửa trở nên lộn sộn
Mình đã thử sửa header của nó nhưng vẫn không mở được.khá là bế tắc,nhưng sau đó mình để ý đến các byte height và weight của nó thì thấy có vẻ không ổn(tất cả các byte = 0)
image
![image](https://user-images.githubusercontent.com/95273832/181786037-7fd41d53-eb2f-4cfa-9f67-f83d81afda52.png)

Ban đầu mình đã cố gắng chỉnh thủ công bằng việc tăng giá trị của height và weight nhưng đều không được ,đoạn này mình bị stuck rất là lâu.

Sau khi tìm hiểu thêm về file PNG thì mình biết thêm là Height x Weight phải nhỏ hơn size của file ảnh. Lúc này mình đã nghĩ tới brute force ảnh để tìm được width và length thích hợp.
Lục lọi mò mẫm khắp trên google thì mình cũng tìm được 1 đoạn code python để tìm ra size tương ứng cho bức ảnh :>

```php
from zlib import crc32

data = open("flag.png",'rb').read()
index = 12

ihdr = bytearray(data[index:index+17])
width_index = 7
height_index = 11

for x in range(1,2000):
	height = bytearray(x.to_bytes(2,'big'))
	for y in range(1,2000):
		width = bytearray(y.to_bytes(2,'big'))
		for i in range(len(height)):
			ihdr[height_index - i] = height[-i -1]
		for i in range(len(width)):
			ihdr[width_index - i] = width[-i -1]
		if hex(crc32(ihdr)) == '0x612055aa':
			print("width: {} height: {}".format(width.hex(),height.hex()))
	for i in range(len(width)):
			ihdr[width_index - i] = bytearray(b'\x00')[0]
```

![image](https://user-images.githubusercontent.com/95273832/181786395-a5e5886f-362c-422a-994c-af8af0dc2a8b.png)

Ohohohohoh,chỉnh hex và nhận flag thôi

![image](https://user-images.githubusercontent.com/95273832/181786484-ff71a37c-339a-4e32-a9e9-4917d759bff1.png)

![image](https://user-images.githubusercontent.com/95273832/181786506-d996ec02-c46d-4f0b-842f-2cf69511d4a6.png)

FLAG: FPTUHacking{ju5t_ba5s1c_1HdR_r1ght}
