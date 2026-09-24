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

