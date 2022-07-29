-Chúng ta có 1 file zip,sau khi unzip xong thì chúng ta có 1 mớ hỗn độn và bị đi vào bế tắc
Chúng tôi thử “file” cái file được unzip ra xem nó là gì(và nó là định dạng của file system linux nên chúng tôi đã sử dụng “FTK imager” để đọc thông tin bên trong của nó)
![image](https://user-images.githubusercontent.com/95273832/181786733-7243d1d7-3e6c-4009-9417-f7cb9973ceab.png)

-Chúng tôi tìm được 1 số file trống và 2 file có chứa dữ liệu
![image](https://user-images.githubusercontent.com/95273832/181786835-70da764a-44fa-47fb-9323-a21a79b41112.png)
![image](https://user-images.githubusercontent.com/95273832/181786920-b1228402-f2cc-4909-ab9c-e653999f5247.png)

-Nhận ra được file mp3(cứ ngỡ là sẽ có flag rồi ,nhưng không,lại bế tắc tiếp khi nó thật sự như tiêu đề của nó”just a song”.lại bó tay tiếp và ngồi mò mẫm tìm  tool recover file khi chúng tôi thấy file kết thúc bằng “LAME 3.9..5” (là bộ mã hóa MPEG Audio Layer III (MP3) chất lượng cao)
vì nghĩ rằng có thể nó đã bị mất mát dữ liệu trong quá trình encode(sai lầm  .-. .-.)
![image](https://user-images.githubusercontent.com/95273832/181787015-72048760-3ac3-4a5e-b7a8-d05fb61f252a.png)

Thật bất ngờ khi chúng tôi cho nó vào hex editer,chúng tôi đã nhìn thấy “P.K” và “f.l.a.g.t.x.t”
và đã nhận ra đó là 1 file zip đã bị sửa,làm sai định dạng của file zip “PK”.Sau khi cắt nó sang 1 file hex khác thì chúng tôi nhận ra rằng file zip đã bị chèn bit “00” vào giữa 2 bit.và công cuộc cày cuốc ngồi xóa từng bit “00” bắt đầu.
![image](https://user-images.githubusercontent.com/95273832/181787052-4a21d388-418f-4717-838f-28dcf0bd505a.png)

Cũng có 1 vấn đề nhỏ là file zip này đã bị encode với mật khẩu.nhưng so easy ,chúng tôi đã crack được nó(https://linuxconfig.org/how-to-crack-zip-password-on-kali-linux)

![image](https://user-images.githubusercontent.com/95273832/181787090-94d7c139-70d4-4214-af32-35b1c892a242.png)

![image](https://user-images.githubusercontent.com/95273832/181787145-38c8f86a-b729-4bf0-8360-fdc4cfaa82ab.png)

FLAG:FPTUHacking{1265654407417514740_wouldn_t_you_say_there_s_a_light_in_the_darkest_moment}
