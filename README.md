# OverTheWire-Bandit-Writeups
Nhật ký giải bài tập OverTheWire Bandit của tôi.
 Thông tin về sever:portnumber 2220,ip:bandit.labs.overthewire.org
*BANDIT0-Mục tiêu của màn chơi này là bạn đăng nhập vào trò chơi bằng SSH. Máy chủ mà bạn cần kết nối là bandit.labs.overthewire.org , trên cổng 2220. Tên người dùng là bandit0 và mật khẩu là bandit0
- về ssh: tôi hiểu nó là một giao thức bảo mật mạng nằm kết nối trao đổi thông tin giữa các sever với nhau với sự bảo mật an toàn
-công thức đăng nhập vào sever: ssh -p -portnumber username@ip
+cụ thể bandit level 0: ssh -p -2220  bandit0@bandit.labs.overthewire.org
-sau khi đăng nhập vào rồi , ta được yêu cầu nhập mật khẩu, chúng ta chỉ việc nhập pass theo sever đã cung cấp là bandit0
=> như vậy là đã hoàn thành thao tác đăng nhập vào sever day1
==>usename :bandit0 pass:bandit0

 
 
 
 
 
 
 
 
 
 # BANDIT level 0-1:Mục tiêu cấp độ
Mật khẩu cho cấp độ tiếp theo được lưu trữ trong một tệp có tên là... Tệp readme nằm trong thư mục chính. Sử dụng mật khẩu này để đăng nhập. Đăng nhập vào bandit1 bằng SSH. Bất cứ khi nào bạn tìm thấy mật khẩu cho một cấp độ, Hãy sử dụng SSH (cổng 2220) để đăng nhập vào cấp độ đó và tiếp tục trò chơi. 
## Như yêu cầu mà trò chơi đã cung cấp thì ta cần vào tệp readme để kiểm tra mật khẩu tiếp theo, vậy ta làm bằng cách nào,để giải quyết vấn đề này ta cần nắm rõ một số lệnh:
### ls: yêu cầu server trích xuất list các tệp nằm trong server
### ls -la: cũng giống như ls nhưng ta được xem thông tin một cách cụ thể hơn
### cat <tentep>: đọc tệp <tentep> ra và hiển thị ra màn hình
### cd <tenthumuc> : đi vào thư mục chỉ định
### file <tentep>: kiểm tra định dạng của file
### du <tentep>:kiem tra dung lượng, bộ nhớ của file(du -b <tentep>:kiểm tra byte của file,du -h <tentep> kiểm tra gb,mb,tb của file)
### find : tìm kiếm tệp và thư mục
## thao tác solve bandit 0-1 như sau:
### trước hết ta dùng ls để kiểm tra xem có những file vào trong server
### sau khi đã thấy file trong server ( cụ thể ở bài này là file readme) ,ta dùng "cat readme" để đọc và in file ra và nhìn thấy được mật khẩu mà server cung cấp cho tài khoản bandit1
====> user: bandit1 pass:6y2kwnwK6grgvwvpvLaa2T1cpFEKOhNR 





# BANDIT LEVEL 1-2 :Mật khẩu cho cấp độ tiếp theo được lưu trong một tệp có tên là - nằm trong thư mục chính 
## có thể thấy mục đích chính của bài này là đọc được file "-" vì trong đó có chứa mật khẩu của bandit 2
## dựa vào kiến thức từ trước , ta có thể dùng lệnh cat để đọc file tên là "-" nhưng vì "-" là một kí tự đặc biệt khác với tên thông thường nên khi chúng ta sử dụng cần sử dụng đúng cách, cụ thể là cat ./-
## sau khi thực thi lệnh xong thì sẽ hiện thị mật khẩu cho chúng ta
===> user:bandit2 pass:PK8fYLZg2hnHSz83plBL1iEPKdD3QToB






# BANDIT LEVEL 2-3:Mật khẩu cho cấp độ tiếp theo được lưu trữ trong một tệp có tên là... --spaces in this filename--nằm trong thư mục chính 
## cũng tương tự như các bài trước thì ở bài tập này cũng chỉ là yêu cầu truy cập vào file có tên"--spaces in this filename--" nằm trong thư mục chính là đã có thể nhìn thấy mật khẩu của bandit3
## Tuy nhiên ở bài này thì chúng ta sẽ cần phải cân nhắc bởi vì filename này có chứa dấu cách, vì vậy khi nhập tên file cần thêm " ở hai đầu để server có thể đọc đúng tên file
## Cụ thể với bandit trên thì ta nhập như sau: cat ./"--spaces in this filename--"
==> username :bandit3 pass:7ZZ2LFrykP2zEyvBl4m3clcL7tGYJPME







# BANDIT LEVEL 3-4:Mật khẩu cho cấp độ tiếp theo được lưu trữ trong một tệp ẩn trong... trong thư mục này. 
## Ở bài toán này ta , vì inhere là một thư mục vì vậy ta cần dùng lệnh cd để nhảy đến thư mục đó 
## Sau khi đã nhảy đến được thư mục inhere,thông thường ta sẽ dùng ls để nhìn thấy danh sách file trong thư mục này nhưng vì đây là một file ẩn nên thay vì dùng ls ta phải thay bằng ls-la
### ls-la: dùng để liệt kê danh sách file ẩn trong thư mục
## Sau khi đã biết được file ẩn đó thì việc còn lại chỉ đơn giản là đọc và in ra file đó ,cụ thể trong bài này là ta cat ...Hiding-From-You
==>username:bandit4 pass:xzTXq1rDJQVVAzdv5cHq1TQytTWufAMq




# BANDIT LEVEL 4-5:Mật khẩu cho cấp độ tiếp theo được lưu trữ trong tệp duy nhất mà con người có thể đọc được. tập tin trong thư mục inhere . Mẹo: nếu thiết bị đầu cuối của bạn bị lỗi Hãy thử lệnh “reset”. 
## Vẫn truy cập vào folder inhere như thông thường
## Nhưng vì ở bài này chỉ có một file mà con người có thể đọc được Vì vậy ta nghĩ đến lệnh file( để xem thông tin về định dạng của file)
## Trong trường hợp bài này, ta dùng lệnh file./*(vì lệnh này kiểm tra định dạng file của các tệp trong thư mục) khác với file ./ là kiểm tra định dạng của thư mục 
## ta có thể biết thêm: ở định dạng asc ii text (định dạng này là định dạng mà con người có thể thấy được)
## cuối cùng ta khi ta đã biết cần đọc file nào rồi, ta chỉ cần cat ./-file007  là có thể thấy được pass( cat ./ dùng để đọc các file có kí tự đặc biệt được học ở bài cũ)
==>username:bandit5 pass:6C7h9GD8M6ai5nr7wo1RonrzFjj9yIrG




# BANDIT LEVEL 5-6:Mật khẩu cho cấp độ tiếp theo được lưu trữ trong một tệp nào đó dưới Thư mục inhere có tất cả các thuộc tính sau:
dễ đọc đối với con người
Kích thước 1033 byte
không thể thực thi
## Vẫn như các bài tập khác điều đầu tin là ta truy cập vào thư mục inhere : cd inhere
## ở bài này ta học thêm được 1 cú pháp mới nhằm tìm chi tiết file theo yêu cầu: find . -type f -size 1033c ! -executable
## . dùng để tìm ở file hiện tại , size: tìm kích cỡ dung lượng của file , 1033c tương ứng với 1033byte , ! dùng để phủ định ( không thể thực thi), còn nếu không có ! thì có thể hiểu là có thể thực thi
##### type f: tệp thông thường, type d: thư mục
## sau khi find ra tệp theo yêu cầu mà ta cần rồi việc còn lại chỉ là dùng cat để in pass ra thôi (cat ./maybehere07/.file2)
==>username:bandit6 pass:pXa26xhMWaC2SvDotA4r9EgZkulOeSBW









# BANDIT LEVEL 6-7:
Mật khẩu cho cấp độ tiếp theo được lưu trữ ở đâu đó trên... máy chủ và có tất cả các thuộc tính sau:Thuộc sở hữu của người dùng bandit7
    thuộc sở hữu của nhóm bandit6
    Kích thước 33 byte
## trước khi vào bài này tôi cần hiểu lại một lệnh dễ gây nhầm lẫn là cat <name> và cat ./<name>
### cat<name>: in ra file có tên thông thường
### cat ./<name>: in ra file có tên bắt đầu bằng "-"
## sau khi hiểu được 2 lệnh trên ta tiếp tục bài làm, vì đề bài bảo rằng file nằm ở đâu đó trên server nên ta nghĩ ngay đến việc find / ( vì lệnh này có thể tìm trong server chứ không riêng chỉ là thư mục và tệp )
## ta lần lượt thực hiện cú pháp như sau: find / -user bandit7 -group bandit6 -size 33c 2>/dev/null   (-user dùng để tìm theo tên, -group để tìm theo nhóm ,-size để tìm theo kích cỡ bộ nhớ, 2>/dev/null để khắc phục lỗi( > dùng để điều hướng ,2> tức là đẩy luồng báo lỗi cụ thể là luồng 2 ra chỗ khác còn /dev/null coi như thùng rác nơi vứt rác luồng 2 bị lỗi vào))
## sau khi find được tệp cần tìm rồi thì ta chỉ cần cat <name> như ở đoạn đầu ta đã nói là có thể in ra được password  của bandit7 (cat /var/lib/dpkg/info/bandit7.password)
==>username:bandit7 pass:Bmnnvf82KzQlfxgAI2d1zYbr1u9pr3E3


# BANDIT LEVEL 7-8:Mật khẩu cho cấp độ tiếp theo được lưu trong tệp data.txt. bên cạnh từ "một phần triệu(millionth)" 
## ở bài này khi ta chưa biết đến lệnh grep thì có thể ta sẽ nghĩ đến find đầu tiên nhưng với bài này vì đã biết được thông tin  từ khóa (millionth) nên ta nên biết đến grep : lệnh dùng để tìm kiếm theo từ khóa
### một số dạng grep cần biết: grep -? "tentukhoa" <tentep>
### ?=i thì không phân biệt in hoa in thường
### ?=v thì phủ định , in ra các tệp không chứ từ khóa
### ?=n thì in ra dòng chứa từ khóa
### ?=E thì tìm kiếm từ khóa nâng cao được nhiều từ 1 lúc, cú pháp như sau:grep -E "tk1|tk2|..." <tentep>
### Ta cũng có thể kết hợp lại với nhau để đạt hiệu quả tìm kiếm ví dụ: -iE -in ....
## khi tìm kiếm được ta thấy dòng :millionth       VR1ljMayciFxbnUokuQmJFw6QC9VKtub (millionth có nghĩa là 1/1 triệu) và như vậy là ta tìm được password
==>username:bandit8 pass:VR1ljMayciFxbnUokuQmJFw6QC9VKtub







# BANDIT LEVEL 8-9:Mật khẩu cho cấp độ tiếp theo được lưu trong tệp data.txt. và là dòng văn bản duy nhất chỉ xuất hiện một lần. 
## đến với bài này ta cần phải tiếp xúc với lệnh mới lại đó là sort và uniq
### để thực sự biết cách giải level này trước tiên ta cần biết cách hoạt động và cú pháp của chúng:
#### cú pháp sort : sort -? <tentep> , và ở bài này ta chưa cần dùng đến -? mà chỉ cần đơn giản là sort <tentep>: lệnh này dùng để sắp xếp các thông tin trong tệp mặc định là theo thứ tự alphabet, khác với cat là chỉ đọc tệp theo thứ tự random
#### cú pháp uniq: uniq -? (ở bài này ta sử dụng uniq -u ví uniq -u có chắc năng lọc các dòng trùng nhau và chỉ giữ lại các dòng không bị trùng lặp) . Và một lưu ý nhở với lệnh uniq này là chúng không đi một mình mà cần đi kèm sau lệnh sort bởi lệnh này cần được sắp xếp trước thì mới lọc được một cách chính xác
#### ở uniq này ta có thể biết thêm vì uniq -d: lọc ra những dòng bị trùng lặp(đối ngược với uniq -u), uniq -c: đếm số lần xuất hiện của từng dòng
#### cú pháp để uniq đi kèm với sort : sort -? <tentep> | uniq -? 
### sau khi đã tìm ra được dòng duy nhất chỉ xuất hiện 1 lần( đúng theo yêu cầu của đề bài) thì đó cũng chính là password
==>username:bandit9 pass:EjmOSvuAu7sGAHqHVcBDPirRe9T03kxl





# BANDIT LEVEL 9-10 :Mật khẩu cho cấp độ tiếp theo được lưu trong tệp data.txt. trong một trong số ít chuỗi ký tự mà con người có thể đọc được, đứng sau một vài dấu '='. các nhân vật. 
## ở level này lúc đầu bắt đầu bài toán tôi đã nghĩ rằng có thể dùng grep để tìm kí tự "=" là có thể giải quyết bài toán nhưng không được và bị báo lỗi" binary file matches" có thể hiểu đơn giản là grep không thể đọc toàn bộ thông tin trong tệp chứa nhiều kí tự nhị phân này cho nên ta cần hướng đến một lệnh mới đó là strings
## cách sử dụng của lệnh này cũng khá đơn giản  : strings <tentep> : lọc ra các chuỗi kí tự mà con người có thể đọc và hiểu được ví dụ : [==p+ , =zW} 
## nhưng để có thể tìm ra được mật khẩu ta cần sử dụng kết hợp cùng lệnh grep nữa bởi đề bài cho ta thông tin rằng có một số kí tự "=" đứng trước pass, ta liền nghĩ ngay đến lệnh grep "="
## đi vào thực chiến ta nhập như sau: strings data.txt | grep "=" 
## sau khi thực hiện lệnh xong ta dễ dòng có thể nhìn thấy dòng :========== B0s2khmbT9u0geKuOoVGW3JZKhndE3BG hoàn toàn khớp với từng yêu cầu mà đề bài đưa ra
==>username :bandit10 ,pass :B0s2khmbT9u0geKuOoVGW3JZKhndE3BG





# BANDIT LEVEL 10-11:Mật khẩu cho cấp độ tiếp theo được lưu trong tệp data.txt . chứa dữ liệu được mã hóa base64 
## ở bài này thì cũng khá đơn giản nếu biết được lệnh base64 
### về cú pháp sử dụng của base64 chỉ cần đơn giản là base64 -d <tentep>: tức là giải mã  các kí tự ở dạng base64 về dạng văn bản thông thường
## đi vào thực hành ta thực hiện lệnh như sau: base64 -d data.txt nó sẽ in ra dòng:The password is pYfOY6HwUsDj5rL9UvyhU7MCmv8vN5Ro
==>username:bandit11, pass:pYfOY6HwUsDj5rL9UvyhU7MCmv8vN5Ro




 # BANDIT LEVEL 11-12:Mật khẩu cho cấp độ tiếp theo được lưu trong tệp data.txt . trong đó tất cả các chữ cái viết thường (az) và viết hoa (AZ) đã được xoay 13 vị trí 
## ở bài này khá khó hiểu được chi tiết cụ thể nếu chưa tiếp xúc với lập trình bao giờ, như đề bài ta hiểu là với mỗi chứ trong văn bản ban đầu xoay 13 vị trị thì sẽ ra được dãy là password. lấy ví dụ đơn giản là a->n,b-o,A->n,B-O,Z-M,z-m
## tiếp theo có một lệnh mới ta cần phải hiểu để solve bài này đó là lệnh tr(translate),cách sử dụng cũng khá đơn giản thôi: tr "daybandau" "daysaukhithaydoi"
## ứng dụng vào bài cụ thể ta kết hợp cùng cat nữa ( để in ra màn hình password sau khi đã xoay 13 vị trí ): cat data.txt | tr "a-zA-Z" "n-za-mN-ZA-M"
## ở đoạn tr rất khó hiểu , ban đầu tôi đã phải thử nhiều lần theo suy nghĩ nhưng bây giờ tôi đã hiểu cách vận hành của nó,bạn có thể hiểu đơn giản rằng : "a-zA-Z" có nghĩa là cho 2 dãy ban đầu là a->z và A-Z
### với dãy a-z thì ta biến đổi thành một dãy mới là dãy n-z nối với dãy a-m (n-za-m)
### tương tự với dãy A-Z thì ta biến đổi thành một dãy mới là dãy N-Z nối với dãy A-M(N-ZA-M)
## sau khi thực thi lệnh thì ta có thể thấy trên màn hình:The password is GROozWPO8QyN0mGrjUkID0WCYkZiQxrN . và đây cũng chính là pass của level này
==>username:bandit12 ,pass:GROozWPO8QyN0mGrjUkID0WCYkZiQxrN 





# BANDIT LEVEL 12-13:Mật khẩu cho cấp độ tiếp theo được lưu trong tệp data.txt . Đây là bản hiển thị dạng hex của một tập tin đã được nén nhiều lần. Ở cấp độ này, việc tạo một thư mục con dưới /tmp có thể hữu ích. Bạn có thể làm việc với nó. Sử dụng lệnh `mkdir` với tên thư mục khó đoán. Hoặc tốt hơn hết, hãy sử dụng lệnh “mktemp -d”. Sau đó sao chép tập tin dữ liệu bằng lệnh cp và đổi tên nó bằng lệnh mv (đọc hướng dẫn). (trang hướng dẫn sử dụng!) 
## haizz quả thực đây là một nhiệm vụ khó , tôi đã phải dành ra 1h để hiểu được 80% cách giải quyết bài này một cách bản chất nhất
## đầu tiên khi chưa biết đến hex mà đọc đề thì thấy nó được lưu trong tệp data.txt tôi liền cat data.txt và tưởng ngon ăn nhưng không hiển thị trước tôi là một loại đống mã nhị phân, nó là cả một hành trình dài ở phía trước
## sau khi đọc và biết cách sử dụng xxd thì tôi lại một lần nữa thử xxd nhưng nó báo lỗi permission denied(bị từ chối quyền) . sau khi tìm hiểu lý do thì tôi mới hiểu rằng cần phải tạo một file mới có thể truy cập được cấp quyền và ở bài này tôi sử dụng mktemp -d : lệnh này dùng để tạo một thư mục tạm thời với tên bất kì để tăng tính bảo mật
## sau khi đã tạo được tệp mới xong( cụ thể với lần tạo của tôi là /tmp/tmp.rHe6WNijCW) thì ta nhảy vào tệp này bằng cách cd ( cụ thể là cd /tmp/tmp.rHe6WNijCW)
## sau khi đã nhảy vào tệp này rồi ta coppy toàn bộ tệp này về home bằng cách cp ~/data.txt . tức là copy dữ liệu từ data.txt sang .(. ở đây tức là thư mục hiện tại để lát nữa có thể truy cập)
## sau khi đã coppy thì lúc này ta hoàn toàn có thể dịch mã nhị phân thành mã thường sang một file mới cụ thể cách làm như sau : xxd -r data.txt > data_raw ( điều này có nghĩa là tạo ra file data_raw chứa nội dung dịch từ mã nhị phân sang mã thường)
##  ta tiếp tục kiểm tra xem định dạng file của file data_raw như nào , ta thực hiện file data_raw, lúc này ta thấy một thông báo rằng:data_raw: gzip compressed data, was "data2.bin", last modified: Sat Sep 26 21:52:56 2026, max compression, from Unix, original size modulo 2^32 582. nó có nghĩa là file này cần được giải nén thông qua công cụ gzip . Để thực hiện điều này, trước mắt ta cần biết lệnh mv: lệnh dùng để rename ( muốn dùng công cụ gzip để giải nén file trước hết file đó cần được giải nén dưới dạng <tentep>.gz  vì vậy ta dùng lệnh mv để rename)
## có một lưu ý nhỏ ở đâu là ta thường để tên <tentep>.gz với tên tệp giống "data2.bin" để tránh nhầm lẫn giữa tên cũ và tên mới
## ta bắt đầu thực hiện: mv data_raw data2.gz
## sau đó t giải nén file bằng cách grip -d data2.gz ( grip -d có nghĩa là giải nén, câu lệnh này đang giải nén tệp data2.gz). sau khi giải nén xong ta tiếp tục kiểm tra định dạng xem đã có thể xem dưới dạng ascii chưa (file data2)
## lúc này lại hiện thêm thông báo:data2: bzip2 compressed data, block size = 900k . câu thông báo này có ý nghĩa là file lại cần được giải nén bằng công cụ bzip2 . ta vẫn tiếp tục làm tương tự như gzip
## mv data2 data2.bz2 -> bzip2 -d data2.bz2 -> file data2-> tiếp tục thấy dạng gzip ta làm tương tự như các lần trên ,đến một lúc ta lại thấy một thông báo mới:data4: POSIX tar archive (GNU). với thông báo này ta cần dùng tar -xf <tentep> để xả gói file. ta thực hiện như sau:tar -xf data4 . sau đó ta dùng ls -l để coi danh sách chi tiết xem có file nào được sinh ra không, ở bash mà tôi đang làm thấy xuất hiện file mới là data5.bin lúc này ta lại xem định dạng của data5.bin như nào(file data5.bin) thì này thấy cần xả gói tar ta lại cứ tiếp tục như vậy khi gặp thông báo tar thì mình dùng tar -xf khi nào gặp thông báo gzip thì mình dùng gzip, bzip2 thì dùng bzip cứ thế đến data9.
## lúc này khi file data9 thì ta đã thấy xuất hiện ascii text ( thứ mà ta sẽ đọc được)
## phần còn lại chỉ là việc cat ra và thấy được password
## bandit12@bandit:/tmp/tmp.rHe6WNijCW$ cat data9 The password is qQYQiHOBPR8zR61qxYqX45quvihF2uzk
==>username: bandit13 ,pass:qQYQiHOBPR8zR61qxYqX45quvihF2uzk







# BANDIT LEVEL 13-14:Mật khẩu cho cấp độ tiếp theo được lưu trữ trong /etc/bandit_pass/bandit14 và chỉ có thể được đọc bởi người dùng bandit14 . Ở cấp độ này, bạn không nhận được mật khẩu tiếp theo, nhưng bạn... Nhận khóa SSH riêng tư có thể được sử dụng để đăng nhập vào cấp độ tiếp theo. Hãy xem lại các lệnh đã giúp bạn đăng nhập vào các cấp độ cướp trước đó. và tìm hiểu cách sử dụng chìa khóa cho cấp độ này.
## bước vào bài này trước hết ta cần biết được địa chỉ chính xác của sshkey.private là nằm ở đâu?
##  ta kết nối với máy chủ bandit13 thông qua pass của level trước: ssh -p 2220 bandit13@bandit.labs.overthewire.org rồi nhập mật khẩu để kết nối
## sau khi kết nối ta dùng lệnh pwd: dùng để biết xem mình đang ở đâu , thư mục nào, thì ta thấy được /home/bandit13 và sau đó ta thử dùng lệnh ls để liệt kê các file nằm trong home/bandit13 thì thấy có sshkey.private => như vậy ta xác định được sshkey.private có đường dẫn cụ thể là : home/bandit13/sshkey.private
## và ở bước này ta cần dùng exit để out server bandit13 bởi key không cấp quyền cho bandit13
## sau khi biết được địa chỉ chính xác rồi ta dùng : scp -P 2220 bandit13@bandit.labs.overthewire.org:/home/bandit13/sshkey.private ./bandit14.key  
## ta đi vào phân tích từng lệnh cụ thể như sau
### scp : dùng để sao chép dữ liệu giữa các server với nhau
### khác với ssh thì scp thì dùng -P( viết hoa) 2220 cái này ý nghĩa cũng giống như ssh tức là cổng 2220
### bandit13@bandit.labs.overthewire.org:/home/bandit13/sshkey.private : lệnh này có ý nghĩa là dữ liệu của sshkeyprivate ở địa chỉ cụ thể nhất để có thể copy dữ liệu một cách chính xác nhất
### ./bandit14.key : ở đây . ý muốn nói là thư mục hiện tại và /bandit14.key tức là đặt tên cho file key này là bandit14.key
### HIỂU ĐƠN GIẢN TOÀN BỘ DÒNG LỆNH TRÊN LÀ: HÃY SAO CHÉP sshkey.private trong server bandit13 thông qua cổng 2220 , SAO CHÉP VÀO THƯ MỤC HIỆN TẠI và đặt tên file đó là bandit14.key
## tiếp theo để tăng tính bảo mật và giới hạn quyền truy cập ta cần thực hiện thêm lệnh : chmod 600 bandit14.key (chmod(change mode): thay đổi chế độ, 6 0 0 có ý nghĩa lần lượt là 6(tôi có thể đọc và truy cập tệp này) , 0( không có group nào có thể truy cập file này),0( không có cá nhân nào khác có quyền truy cập tệp này)
## sau khi đã đảm bảm chỉ mình mới có thể truy cập vào tệp này rồi thì  bước còn lại là : ssh -i bandit14.key bandit14@bandit.labs.overthewire.org -p 2220
### ở câu lệnh này chỉ khác ssh thông thường ở chỗ thay vì đăng nhập bằng cách nhập mật khẩu thông thường thì ta đăng nhập vào server bằng key cụ thể là -i bandit14.key
### hiểu cả câu: truy cập vào server bandit14@bandit.labs.overthewire qua port 2220 và đăng nhập bằng bandit14.key thay vì dùng cách nhập mật khẩu
## vì theo đề bài : mật khẩu ở trong /etc/bandit_pass/bandit14 nên lúc này ta chỉ cần : cat /etc/bandit_pass/bandit14 là có thể lấy được key
==>username:bandit14, pass:aaWecNkG4FhxJQxz07uiwzVP6bJiYS65
