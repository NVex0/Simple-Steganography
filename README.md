# Simple-Steganography

Title của Challenge có hint về steghide.

Nếu bạn newbie thì hiểu sơ sơ là giấu tin vào bên trong 1 ảnh.

Steghide có thể require pass hay không tuỳ vào cái ông giấu tin.

Mình thử extract không cần pass trước nhưng có vẻ không được, vì thế giờ mình đi tìm pass :D

`strings` của file khá ngắn, dò từng dòng được, nhưng không có gì là readable cả.

Mình dùng `exiftool` thì để ý mục `keywords : myadmin`

Thử extract với password là "myadmin":

`steghide extract -sf Minions1.jpeg -p myadmin`

Thì extract được 1 file là "raw.txt".

`cat raw.txt` thì thấy 1 chuỗi ở base64. Decode nó ra:

`cat raw.txt | base64 -d'

`Flag: CTFlearn{this_is_fun}`

