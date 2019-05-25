# DC_Assignments

# Note cho [3]CORBA

```Đây là hướng dẫn cho bài 3 CORBA

Để chạy được phải dùng java 8. Có thể dùng tạm thời 1 Session (sau đó nó sẽ hết) bằng cách gõ vào Terminal:

JAVA_HOME=/usr/lib/jvm/java-8-openjdk-amd64

PATH=$JAVA_HOME/bin:$PATH

Sau đó để generate java files từ .idl file dùng:

idlj -fall <tên-file.idl>

Ví dụ: idlj -fall Cacl.idl

Tiếp, compile tất cả các .java files:

javac *.java ./CaclApp/*.java

Ok, giờ chúng ta có thể chạy. Các bước như sau:

orbd -ORBInitialPort <số-port>&                                                         //ví dụ: orbd -ORBInitialPort 1050&

java <tên-main-class-của-server> -ORBInitialPort <số-port> -ORBInitialHost localhost&        //ví dụ: java CaclServer ... (... có nghĩa viết tiếp)

java <tên-main-class-của-client> -ORBInitialPort <số-port> -ORBInitialHost localhost        //ví dụ: java CaclClient ... (... có nghĩa viết tiếp)