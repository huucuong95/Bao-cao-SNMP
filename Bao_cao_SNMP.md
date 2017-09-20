<html>
 <body>
  <h1 id="tim-hieu-ve-snmp">
   Tìm hiểu về SNMP
  </h1>
  <h2 id="1-snmp-la-gi">
   1, SNMP là gì?
  </h2>
  <p>
   Simple Network Management Protocol (SNMP) là một giao thức lớp ứng dụng được định nghĩa bởi Internet Architecture Board (IAB) trong RFC1157 để trao đổi thông tin quản lý giữa các thiết bị mạng. Nó là một phần của bộ giao thức TCP/IP.
   <br/>
   SNMP là một trong những giao thức được chấp nhận rộng rãi để quản lý và giám sát các thành phần mạng. Hầu hết các thiết bị đều được cài đặt sẵn SNMP. Nhưng chúng ta chúng ta cần phải kích hoạt và được cấu hình để liên lạc với network management system (NMS)
   <br/>
  <p align="center"> 
  <img src="http://i.imgur.com/MABskd0.png">
  </p>
  </p>
  <h2 id="2-snmp-manager">
   2, SNMP Manager
  </h2>
  <p>
   Một người quản lý hoặc một hệ thống quản lý là một thực thể riêng biệt có trách nhiệm giao tiếp với các SNMP agent trên các thiết bị mạng. Đây thường là một máy tính được sử dụng để chạy một hoặc nhiều hệ thống quản trị mạng.
   <br/>
   Các chức năng chính của trình quản lý SNMP:
   <br/>
   - Truy vấn agent
   <br/>
   - Nhận phản hồi từ agent
   <br/>
   - Đặt các biến trong các agent
   <br/>
   - Nhận các sự kiện không đồng bộ từ các agent
  </p>
  <h2 id="3-cac-thiet-bi-uoc-quan-ly">
   3, Các thiết bị được quản lý
  </h2>
  <p>
   SNMP quản lý các thiết bị máy chủ hoặc các thiết bị mạng. Ví dụ như như: router, switch, server, máy in …
  </p>
  <h2 id="4-snmp-agent">
   4, SNMP agent
  </h2>
  <p>
   Agent là một chương trình đóng gói trong các thành phần mạng. Cho phép agent cho phép thu thập cơ sở dữ liệu từ các thiết bị cục bộ và cung cấp cho SNMP manager khi nó được truy vấn.
   <br/>
   Chức năng SNMP agent:
   <br/>
   - Thu thập thông tin quản lý về mạng nội bộ.
   <br/>
   - Lưu trữ và truy xuất thông tin quản lý được định nghĩa trong MIB.
   <br/>
   - Gắn một sự kiện cho một người quản lý.
   <br/>
   - Như là một proxy cho quản lý một node mạng.
   <br/>
    <p align="center"> 
  <img src="https://www.manageengine.com/network-monitoring/images/snmp-components.gif">
  </p>
  <h2 id="5-quan-ly-thong-tin-co-so-du-lieu-hoac-co-so-quan-ly-thong-tin-mib">
   5, Quản lý thông tin cơ sở dữ liệu hoặc cơ sở quản lý thông tin (MIB)
  </h2>
  <p>
   Mỗi SNMP agent duy trì một thông tin cơ sở dữ liệu mô tả các tham số thiết bị được quản lý. Trình quản lý SNMP sử dụng cơ sở dữ liệu này để yêu cầu agent cung cấp thông tin khi cần cho việc quản lý hệ thống mạng (NMS). Cơ sở dữ liệu được chia sử thường xuyên giữa agent và người quản lý được gọi là cơ sở quản lý thông tin (MIB).
   <br/>
   Thông thường, các MIB này chứa tập hợp các giá trị thống kê và kiểm soát các node này trên mạng. SNMP cũng cho phép mở rộng các giá trị chuẩn này với các giá trị cụ thể cho một agent cụ thể thông qua việc sử dụng MIB riêng.
   <br/>
   Tóm lại, tệp MIB là tập hợp các câu hỏi mà SNMP manager có thể yêu cầu các agent. Agent thu thập dữ liệu tại mạng nội bộ và lưu trữ nó, như được định nghĩa trong MIB. Vì vậy, SNMP manager nên biết những câu hỏi tiêu chuẩn và riêng tư này cho mọi loại agent.
  </p>
  <h2 id="6-cau-truc-mib-va-object-identifier-object-id-or-oid">
   6, Cấu trúc MIB và Object Identifier (Object ID or OID)
  </h2>
  <p>
   Cơ sở quản lý thông tin (MIB) là tập hợp thông tin để quản lý yếu tố mạng. MIB bao gồm các đối tượng được quản lý được xác định bởi Object ID hoặc OID.
   <br/>
   Mỗi Identifier là duy nhất và hiển thị các đặc tính cụ thể của thiết bị được quản lý. Khi được truy vấn, giá trị trả về của mỗi số nhận dạng có thể khác nhau ví dụ: Text, Number, Counter, …
   <br/>
   Một thiết bị hỗ trợ SNMP có thể cung cấp nhiều thông tin khác nhau, mỗi thông tin đó gọi là một object. Ví dụ :
   <br/>
   + Máy tính có thể cung cấp các thông tin : tổng số ổ cứng, tổng số port nối mạng, tổng số byte đã truyền/nhận, tên máy tính, tên các process đang chạy, ….
   <br/>
   + Router có thể cung cấp các thông tin : tổng số card, tổng số port, tổng số byte đã truyền/nhận, tên router, tình trạng các port của router, ….
   <br/>
   Mỗi object có một tên gọi và một mã số để nhận dạng object đó, mã số gọi là Object ID (OID).
   <br/>
   Mỗi OID được tổ chức theo cấp bậc trong MIB. Phân cấp MIB có thể được biểu diễn trong một cấu trúc cây với mã nhận dạng cá thể.
   <br/>
   <p align="center">
   <img href='http://src="https://www.manageengine.com'/>
   <img src="https://www.manageengine.com/network-monitoring/images/mib-oid-tree.gif">
  </p>
  <h2 id="7-lenh-co-ban-cua-snmp">
   7, Lệnh cơ bản của SNMP
  </h2>
  <p>
   Sự đơn giản trong việc trao đổi thông tin đã làm SNMP trở thành một giao thức được chấp nhận rộng rãi. Lý do chính là tập hợp các lệnh đơn giản, chúng được liệt kê dưới đây:
   <br/>
   - GET: thao tác GET là yêu cầu gửi bởi manager tới thiết bị được quản lý. Nó được thực hiện để lấy ra một hoặc nhiều giá trị từ thiết bị được quản lý.
   <br/>
   - GET NEXT: hoạt động tương tự như GET. Sự khác biệt đáng kể là thao tác GET NEXT lấy giá trị của OID kế tiếp trong cây MIB.
   <br/>
   - GET BULK: thao tác GET BULK được sử dụng để lấy dữ liệu lớn từ bảng MIB.
   <br/>
   - SET: thao tác này được manager sử dụng để sửa đổi hoặc chỉ định giá trị của thiết bị được quản lý.
   <br/>
   <p align="center">
   <img src="https://www.manageengine.com/network-monitoring/images/snmp-get-response.gif">
     </p>
   <br/>
   - TRAPS: không giống như các lệnh trên được bắt đầu từ manager SNMP, TRAPS được khởi tạo bởi các agent. Đây là một tín hiệu cho manager SNMP của agent khi có một sự kiện mới.
   <br/>
    <p align="center">
   <img href='http://src="https://www.manageengine.com'/>
   <img src="https://www.manageengine.com/network-monitoring/images/snmp-trap.gif">
      </p>
   <br/>
   - INFORM: lệnh này tương tự như TRAPS do agent khởi xướng, ngoài ra INFORM bao gồm xác nhận manager SNMP khi nhận thông báo.
   <br/>
     <p align="center">
   <img href='http://src="https://www.manageengine.com'/>
   <img src="https://www.manageengine.com/network-monitoring/images/snmp-inform-acknowledgment.gif">
       </p>
   <br/>
   - RESPONSE: đây là lệnh được sử dụng để mang lại giá trị hoặc tín hiệu của các hành động theo chỉ thị của SNMP manager.
   <br/>
   Giao tiếp SNMP điển hình: là một phần của gói giao thức TCP/IP, các gói tin của SNMP được gói như là UDP và gói tin được gói và truyền bởi giao thức Internet. Hình sau sẽ minh họa cho mô hình 4 lớp do Department of Defense (DoD) phát triển:
   <br/>
      <p align="center">
   <img href='http://src="https://www.manageengine.com'/>
   <img src="https://www.manageengine.com/network-monitoring/images/snmp-layers.gif">
        </p>
   <br/>
   Mặc định SNMP sử dụng cổng 161 và TRAP/INFORM sử dụng cổng 162 để truyền tin.
  </p>
  <h2 id="8-cac-phien-ban-cua-snmp">
   8, Các phiên bản của SNMP
  </h2>
  <p>
   Kể từ khi được tạo ra, SNMP đã trải qua các phiên bản nâng cấp. Tuy nhiên phiên bản SNMP v1 và v2c là những phiên bản được sử dụng nhiều nhất của SNMP. Phiên bản SNMP v3 gần đây được sử dụng vì nó được tích hợp nhiều công nghệ hơn so với các phiên bản cũ, nhưng vẫn không được sử dụng nhiều như 2 phiên bản kia.
   <br/>
   - SNMP v1: đây là phiên bản đầu tiên của giao thức được định nghĩa trong RFCs 1155 and 1157
   <br/>
   - SNMP v2c: Đây là giao thức đã sửa đổi, bao gồm các cải tiến của SNMP v1 trong các loại gói tin giao thức, đường vận chuyển, các yếu tố cấu trúc MIB nhưng sử dụng cấu trúc quản trị SNMP v1 hiện có. Nó được định nghĩa trong RFC 1901, RFC 1905, RFC 1906, RFC 2578.
   <br/>
   - SNMP v3: là phiên bản mới và an toàn của SNMP. SNMP v3 cũng tạo điều kiện cấu hình từ xa các thực thể SNMP. nó được xác định bởi  RFC 1905, RFC 1906, RFC 3411, RFC 3412, RFC 3414, RFC 3415.
  </p>
  <h2 id="9-cau-truc-ban-tin-snmp">
   9, Cấu trúc bản tin SNMP
  </h2>
  <p>
   SNMP chạy trên nền UDP. Cấu trúc của một bản tin SNMP bao gồm : version, community và data.
   <br/>
   <p align="center">
   <img href='http://src="http://i.imgur.com'/>
   <img src="http://i.imgur.com/HZ0gq.jpg">
     </p>
   <br/>
   + Version : v1 = 0, v2c = 1, v2u = 2, v3 = 3.
   <br/>
   + Phần Data trong bản tin SNMP gọi là PDU (Protocol Data Unit). SNMPv1 có 5 phương thức hoạt động tương ứng 5 loại PDU. Tuy nhiên chỉ có 2 loại định dạng bản tin là PDU và Trap-PDU; trong đó các bản tin Get, GetNext, Set, GetResponse có cùng định dạng là PDU, còn bản tin Trap có định dạng là Trap-PDU.
  </p>
  <h2 id="10-mo-hinh-lab">
   10, Mô hình lab
  </h2>
  <p>
  <p align="center">
   <img src="https://github.com/huucuong95/Bao-cao-SNMP/blob/master/Selection_051.png"/>
  </p>
  <h2 id="11-cai-at-cacti-tren-ubuntu-1604">
   11, Cài đặt Cacti trên ubuntu 16.04
  </h2>
  <h3 id="a-cai-at-lamp">
   a, Cài đặt Lamp
  </h3>
  <pre><code>sudo apt-get install apache2 mysql-server php libapache2-mod-php
</code></pre>
  <h3 id="b-cai-at-rrdtools">
   b, Cài đặt RRDtools
  </h3>
  <pre><code>sudo apt-get -y install rrdtool
</code></pre>
  <h3 id="c-cai-at-snmp-and-snmpd">
   c, Cài đặt SNMP and SNMPd
  </h3>
  <pre><code>sudo apt-get -y install snmp snmpd
</code></pre>
  <h3 id="d-cai-cacti-and-spine">
   d, Cài Cacti and Spine
  </h3>
  <pre><code>sudo apt-get -y install cacti cacti-spine
</code></pre>
  <p>
   Sau khi chạy lệnh trên sẽ có thông báo
   <br/>
   <p align="center">
   <img href='http://src="https://www.unixmen.com'/>
   <img src="https://www.unixmen.com/wp-content/uploads/2015/01/1.png">
     </p>
   <br/>
   Chọn OK để tiếp tục
   <br/>
   Sau đó có thông báo sau, chọn apache2
   <br/>
    <p align="center">
   <img href='http://src="https://www.unixmen.com'/>
   <img src="https://www.unixmen.com/wp-content/uploads/2015/01/4.png">
  </p>
   <br/>
   Tiếp theo sẽ có thông báo
   <br/>
     <p align="center">
   <img href='http://src="https://www.unixmen.com'/>
   <img src="https://www.unixmen.com/wp-content/uploads/2015/01/2.png">
  </p>
   <br/>
   Chọn yes, khi cài đặt sẽ có bước yêu cầu bạn nhập password cho tài khoản root MySQL của bạn
   <br/>
      <p align="center">
   <img href='http://src="https://www.unixmen.com'/>
   <img src="https://www.unixmen.com/wp-content/uploads/2015/01/3.png">
  </p>
   <br/>
   Cuối cùng sau khi hoàn thành các bước trên ta khởi động dịch vụ lên
   <br/>
   sudo /etc/init.d/snmpd start
   <br/>
   Bây giờ chúng ta có thể truy cập vào địa chỉ “
   <a href='http://ip-của-server/cacti"'>
    http://ip-của-server/cacti"
   </a>
   <br/>
   Lúc này chúng ta sẽ phải đăng nhập mặc định tài khoản và password là “admin”, chúng ta sẽ nhận được yêu cầu đổi password.
   <br/>
   Tiếp theo chúng ta chọn next tất cả các bước.
   <br/>
   Cuối cùng thì trang web sẽ hiện ra như sau:
   <br/>
       <p align="center">
   <img href='http://src="https://www.unixmen.com'/>
   <img src="https://www.unixmen.com/wp-content/uploads/2015/01/9.png">
  </p>
   <br/>
   Tiếp theo thiết lập spine
   <br/>
   Vào theo đường dẫn:  Console -&gt; Cacti Settings -&gt; Poller
   <br/>
   Vào chọn spine như hình dưới
   <br/>
        <p align="center">
   <img href='http://src="https://www.unixmen.com'/>
   <img src="https://www.unixmen.com/wp-content/uploads/2015/01/spine.png">
  </p>
   <br/>
   Tiếp theo bạn chọn vào graphs -&gt; default tree -&gt; Host: Locahost
   <br/>
   Chờ một thời gian (trên 5 phút) bạn sẽ nhận được biểu đồ tương tự biểu đồ sau:
   <br/>
         <p align="center">
   <img src="https://github.com/huucuong95/Bao-cao-SNMP/blob/master/Selection_033.png"/>
  </p>
  <h3 id="e-them-mot-server-e-theo-doi">
   e, Thêm một server để theo dõi
  </h3>
  <p>
   Bạn truy cập vào Devices -&gt; add để thêm một máy đích theo dõi, rồi thêm các nội dung tương tự như dưới đây rồi ấn creat để thêm:
   <br/>
   <p align="center">
   <img src="https://github.com/huucuong95/Bao-cao-SNMP/blob/master/Selection_034.png"/>
     </p>
   <br/>
   Khi này bạn sẽ bị thông báo
   <br/>
   SNMP error
   <br/>
   Để hết bị lỗi này bạn cần cài SNMPd trên máy được quản lý
   <br/>
   Chúng ta chạy lệnh sau:
   <br/>
   sudo apt-get install snmpd
   <br/>
   Sau khi cài đặt gói xong thì chúng ta chỉnh file cấu hình trong /etc/snmp/snmpd.conf thêm dòng “agentAddress  udp:192.168.55.64:161” vào sau “agentAddress  udp:127.0.0.1:161”
   <br/>
   Tiếp theo là khởi động lại dịch vụ bằng lệnh “/etc/init.d/snmpd restart”
   <br/>
   Chờ một chút thì sẽ thấy máy manager hiện kết quả như hình sau:
   <br/>
    <p align="center">
   <img src="https://github.com/huucuong95/Bao-cao-SNMP/blob/master/Selection_036.png"/>
  </p>
  <p align="center">
   <img src="https://github.com/huucuong95/Bao-cao-SNMP/blob/master/Selection_037.png"/>
  </p>
   <br/>
   Tiếp tới để xem được host dưới dạng biểu đồ thì chúng ta cần thêm host vào danh sách. Truy cập theo đường dẫn Graph Trees -&gt; test -&gt; add rồi chọn như hình dưới:
   <br/>
     <p align="center">
   <img src="https://github.com/huucuong95/Bao-cao-SNMP/blob/master/Selection_038.png"/>
  </p>
   <br/>
   Sau đó ấn create để hoàn thành
   <br/>
   Chuyển sang graphs chúng ta sẽ được kết quả tương tự như sau:
   <br/>
      <p align="center">
   <img src="https://github.com/huucuong95/Bao-cao-SNMP/blob/master/Selection_053.png"/>
  </p>
  <h3 id="f-them-gui-mail-thong-bao-cho-server">
   f, Thêm gửi mail thông báo cho server
  </h3>
  <p>
   Để cài đặt gửi mail thông báo ta làm theo các bước sau:
   <br/>
   - Tải và giải nén plugins
   <br/>
   wget -P /usr/share/cacti/site/plugins
   <a href="http://docs.cacti.net/_media/plugin:settings-v0.71-1.tgz">
    http://docs.cacti.net/_media/plugin:settings-v0.71-1.tgz
   </a>
   <br/>
   tar zxvf /usr/share/cacti/site/plugins/plugin:settings-v0.71-1.tgz -C /usr/share/cacti/site/plugins
   <br/>
   Login vào Cacti thêm plugin theo hình dưới:
   <br/>
   <p align="center">
   <img src="https://github.com/huucuong95/Bao-cao-SNMP/blob/master/Selection_041.png"/>
    <img src="https://github.com/huucuong95/Bao-cao-SNMP/blob/master/Selection_042.png"/>
     </p>
   <br/>
   Sau đó chọn setting -&gt; Mail / DNS rồi điền nội dung tương tự hình dưới rồi ấn save để lưu lại.
   <br/>
    <p align="center">
   <img src="https://github.com/huucuong95/Bao-cao-SNMP/blob/master/Selection_040.png"/>
  </p>
   <br/>
   Sau đó chọn sent a test email sẽ được kết quả
   <br/>
     <p align="center">
   <img src="https://github.com/huucuong95/Bao-cao-SNMP/blob/master/Selection_043.png"/>
  </p>
  <h2 id="12-cai-prtg-tren-windows">
   12, Cài PRTG trên Windows
  </h2>
  <p>
   Đầu tiên chúng ta tải gói prtg.zip từ trang chủ theo địa chỉ:
   <br/>
   <a href="https://downloads.paessler.com/prtg/prtg.zip">
    https://downloads.paessler.com/prtg/prtg.zip
   </a>
   <br/>
   Tiếp theo chúng ta mở file lên và thực hiện cài đặt
    <br/>
 <p align="center">
   <img src="https://github.com/huucuong95/Bao-cao-SNMP/blob/master/Selection_044.png"/>
  </p>
   <br/>
   <br/>
   Trong quá trình cài đặt chúng ta sẽ nhận được một thông báo nhập key, nếu không có key chúng ta tick vào lựa chọn dùng thử 30 ngày, thì được dẫn tới web có sẵn key dùng thử 30 ngày.

   Sau khi cài đặt chúng ta có đượ kết quả như hình sau:
   <br/>
   <p align="center">
   <img src="https://github.com/huucuong95/Bao-cao-SNMP/blob/master/Selection_045.png"/>
 </p>
   <br/>
   Chúng ta cũng có thể thấy được biểu đồ một số máy mà máy chúng ta đã kết nối sẵn bằng cách vào mục Devices:
   <br/>
   <p align="center">
   <img src="https://github.com/huucuong95/Bao-cao-SNMP/blob/master/Selection_046.png"/>
 </p>
   <br/>
   Để thêm một máy mới để theo dõi chúng ta chọn theo đường dẫn Devices -&gt; add devices -&gt; chọn bản hệ điều hành mà mình cần
   <br/>
   <p align="center">
   <img src="https://github.com/huucuong95/Bao-cao-SNMP/blob/master/Selection_047.png"/>
 </p>
   <br/>
   Điền thông tin thiết bị bạn muốn theo dõi
   <br/>
   <p align="center">
   <img src="https://github.com/huucuong95/Bao-cao-SNMP/blob/master/Selection_048.png"/>
  </p>
   <br/>
   Kết quả là:
   <br/>
 <p align="center">
   <img src="https://github.com/huucuong95/Bao-cao-SNMP/blob/master/Selection_049.png"/>
  </p>
   <br/>
  <p align="center">
   <img src="https://github.com/huucuong95/Bao-cao-SNMP/blob/master/Selection_050.png"/>
  </p>
  </p>
 </body>
</html>
