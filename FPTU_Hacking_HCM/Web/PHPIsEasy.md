-Khởi đầu chúng ta có 1 con web hiện lên source code PHP

```php
<?php
require "flag.php";
error_reporting(0);
 $md51 = md5( '0gdVIdSQL8Cm' ); 
 $a = @$_GET[ '0ni0n' ]; 
 $md52 = @md5($a); 
 if ( isset ($a)){ 
    if ($a != '0gdVIdSQL8Cm' && $md51 == $md52) { 
        echo "<script>alert('$flag')</script>"; 
    } else { 
        echo "0ni0n{F3k4_Fl4G}"; 
    } 
} 
show_source(__FILE__);
?>
```
Nhìn vào chúng ta có thể thấy là có 1 biến đầu vào “0ni0n”.lỗ hổng ở đây là việc sai sót trong việc dùng toán tử so sánh “==” .
Toán tử “===” sẽ so sánh 2 biến 1 cách chặt chẽ cả về kiểu dữ liệu và giá trị ,còn toán tử “==” sẽ so sánh 2 biến có cùng giá trị nên ví dụ “0ABC” sẽ bằng với “0dABC”.

Khai thác lỗ hổng này,mình dùng 1 input đầu vào có mã hash có thể() = với mã hash của '0gdVIdSQL8Cm'.và bypass
![image](https://user-images.githubusercontent.com/95273832/181785019-45098680-ea6b-4117-9481-a338aee44d22.png)

=> GET FLAG: FPTUHACKING{Md5_bY_pAAs_eZ_H4_H4}

tài liệu tham khảo:
https://github.com/swisskyrepo/PayloadsAllTheThings/blob/master/Type%20Juggling/README.md?fbclid=IwAR1I7iyNDj6xRrOTmHtIg67Q2ksMtGqJ3-SYsbdQm6dnJZaQajWfeiK7llY#php-juggling-type-and-magic-hashes
