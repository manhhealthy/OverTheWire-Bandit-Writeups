# OverTheWire-Bandit-Writeups
Nhật ký giải bài tập OverTheWire Bandit của tôi.
 Thông tin về sever:portnumber 2220,ip:bandit.labs.overthewire.org
*BANDIT0-Mục tiêu của màn chơi này là bạn đăng nhập vào trò chơi bằng SSH. Máy chủ mà bạn cần kết nối là bandit.labs.overthewire.org , trên cổng 2220. Tên người dùng là bandit0 và mật khẩu là bandit0
- về ssh: tôi hiểu nó là một giao thức bảo mật mạng nằm kết nối trao đổi thông tin giữa các sever với nhau với sự bảo mật an toàn
-công thức đăng nhập vào sever: ssh -p -portnumber username@ip
+cụ thể bandit level 0: ssh -p -2220  bandit0@bandit.labs.overthewire.org
-sau khi đăng nhập vào rồi , ta được yêu cầu nhập mật khẩu, chúng ta chỉ việc nhập pass theo sever đã cung cấp là bandit0
=> như vậy là đã hoàn thành thao tác đăng nhập vào sever day1 viet như này ok k

 
 
 
 
 
 
 
 
 
 # BANDIT level 0-1:Mục tiêu cấp độ
Mật khẩu cho cấp độ tiếp theo được lưu trữ trong một tệp có tên là... Tệp readme nằm trong thư mục chính. Sử dụng mật khẩu này để đăng nhập. Đăng nhập vào bandit1 bằng SSH. Bất cứ khi nào bạn tìm thấy mật khẩu cho một cấp độ, Hãy sử dụng SSH (cổng 2220) để đăng nhập vào cấp độ đó và tiếp tục trò chơi. 
## Như yêu cầu mà trò chơi đã cung cấp thì ta cần vào tệp readme để kiểm tra mật khẩu tiếp theo, vậy ta làm bằng cách nào,để giải quyết vấn đề này ta cần nắm rõ một số lệnh:
### ls: yêu cầu server trích xuất list các tệp nằm trong server
### ls -la: cũng giống như ls nhưng ta được xem thông tin một cách cụ thể hơn
### cat <tentep>: đọc tệp <tentep> ra và hiển thị ra màn hình
### cd <tenthumuc> : đi vào thư mục chỉ định
### file <tentep>: kiểm tra định dạng của file
### du <tentep>:kiem tra dung lượng, bộ nhớ của file(du -b <tentep>:kiểm tra byte của file,du -h <tentep> kiểm tra gb,mb,tb của file)
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






