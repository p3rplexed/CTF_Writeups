2.Piece Of Cake 
-Mở đầu chúng ta cũng có 1 con web hiển thị source code PHP
```php
<?php 
include "flag.php"; 
highlight_file(__FILE__); 
error_reporting(0); 
$str1 = $_GET['0']; 

if(isset($_GET['0'])){ 
    if($str1 == md5($str1)){ 
        echo $onion1; 
    } 
    else{ 
        die(); 
    } 
} 
else{ 
    die();    
} 

$str2 = $_GET['1']; 
$str3 = $_GET['2']; 

if(isset($_GET['1']) && isset($_GET['2'])){ 
    if($str2 !== $str3){ 
        if(hash('md5', $salt . $str2) == hash('md5', $salt . $str3)){ 
            echo $onion2; 
        } 
        else{ 
            die(); 
        } 
    } 
    else{ 
        die(); 
    } 
} 
else{ 
    die();    
} 
?> 
```

Ở bài này thì flag sẽ được chia làm 2 phần.Tương tự như bài “PHP is easy”,bài này cũng bị sai sót trong việc sử dụng toán tử “==”

-Với biến ‘0’ chúng ta cần tìm 1 input có thể bằng với mã hash của chính nó.và 2 input khác nhau nhưng có mã hash bằng nhau.
và payload của nó sẽ là 103.245.249.76:49155/?0=0e215962017&1[]=1&2[]=2

=>GET FLAG :  FPTUHACKING{StR1Ngs_c0nCaTeNaT1oN_1s_EaSy_!!!} 
