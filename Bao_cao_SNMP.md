#Tìm hiểu về SNMP
##1, SNMP là gì?
Simple Network Management Protocol (SNMP) là một giao thức lớp ứng dụng được định nghĩa bởi Internet Architecture Board (IAB) trong RFC1157 để trao đổi thông tin quản lý giữa các thiết bị mạng. Nó là một phần của bộ giao thức TCP/IP.
SNMP là một trong những giao thức được chấp nhận rộng rãi để quản lý và giám sát các thành phần mạng. Hầu hết các thiết bị đều được cài đặt sẵn SNMP. Nhưng chúng ta chúng ta cần phải kích hoạt và được cấu hình để liên lạc với network management system (NMS) 
<img src="http://i.imgur.com/MABskd0.png">
##2, SNMP Manager
Một người quản lý hoặc một hệ thống quản lý là một thực thể riêng biệt có trách nhiệm giao tiếp với các SNMP agent trên các thiết bị mạng. Đây thường là một máy tính được sử dụng để chạy một hoặc nhiều hệ thống quản trị mạng.
Các chức năng chính của trình quản lý SNMP:
- Truy vấn agent
- Nhận phản hồi từ agent
- Đặt các biến trong các agent
- Nhận các sự kiện không đồng bộ từ các agent
##3, Các thiết bị được quản lý
SNMP quản lý các thiết bị quản lý hoặc các thiết bị mạng. Ví dụ như như: router, switch, server, máy in …
##4, SNMP agent
Agent là một chương trình đóng gói trong các thành phần mạng. Cho phép agent cho phép thu thập cơ sở dữ liệu từ các thiết bị cục bộ và cung cấp cho SNMP manager khi nó được truy vấn.
Chức năng SNMP agent:
- Thu thập thông tin quản lý về mạng nội bộ.
- Lưu trữ và truy xuất thông tin quản lý được định nghĩa trong MIB.
- Gắn một sự kiện cho một người quản lý.
- Như là một proxy cho quản lý một node mạng.
<img src="https://www.manageengine.com/network-monitoring/images/snmp-components.gif">
##5, Quản lý thông tin cơ sở dữ liệu hoặc cơ sở quản lý thông tin (MIB)
Mỗi SNMP agent duy trì một thông tin cơ sở dữ liệu mô tả các tham số thiết bị được quản lý. Trình quản lý SNMP sử dụng cơ sở dữ liệu này để yêu cầu agent cung cấp thông tin khi cần cho việc quản lý hệ thống mạng (NMS). Cơ sở dữ liệu được chia sử thường xuyên giữa agent và người quản lý được gọi là cơ sở quản lý thông tin (MIB).
Thông thường, các MIB này chứa tập hợp các giá trị thống kê và kiểm soát các node này trên mạng. SNMP cũng cho phép mở rộng các giá trị chuẩn này với các giá trị cụ thể cho một agent cụ thể thông qua việc sử dụng MIB riêng.
Tóm lại, tệp MIB là tập hợp các câu hỏi mà SNMP manager có thể yêu cầu các agent. Agent thu thập dữ liệu tại mạng nội bộ và lưu trữ nó, như được định nghĩa trong MIB. Vì vậy, SNMP manager nên biết những câu hỏi tiêu chuẩn và riêng tư này cho mọi loại agent.
##6, Cấu trúc MIB và Object Identifier (Object ID or OID)
Cơ sở quản lý thông tin (MIB) là tập hợp thông tin để quản lý yếu tố mạng. MIB bao gồm các đối tượng được quản lý được xác định bởi Object ID hoặc OID.
Mỗi Identifier là duy nhất và hiển thị các đặc tính cụ thể của thiết bị được quản lý. Khi được truy vấn, giá trị trả về của mỗi số nhận dạng có thể khác nhau ví dụ: Text, Number, Counter, …
Một thiết bị hỗ trợ SNMP có thể cung cấp nhiều thông tin khác nhau, mỗi thông tin đó gọi là một object. Ví dụ :
+ Máy tính có thể cung cấp các thông tin : tổng số ổ cứng, tổng số port nối mạng, tổng số byte đã truyền/nhận, tên máy tính, tên các process đang chạy, ….
+ Router có thể cung cấp các thông tin : tổng số card, tổng số port, tổng số byte đã truyền/nhận, tên router, tình trạng các port của router, ….
Mỗi object có một tên gọi và một mã số để nhận dạng object đó, mã số gọi là Object ID (OID).
Mỗi OID được tổ chức theo cấp bậc trong MIB. Phân cấp MIB có thể được biểu diễn trong một cấu trúc cây với mã nhận dạng cá thể.
<img src="https://www.manageengine.com/network-monitoring/images/mib-oid-tree.gif">
##7, Lệnh cơ bản của SNMP
Sự đơn giản trong việc trao đổi thông tin đã làm SNMP trở thành một giao thức được chấp nhận rộng rãi. Lý do chính là tập hợp các lệnh đơn giản, chúng được liệt kê dưới đây:
- GET: thao tác GET là yêu cầu gửi bởi manager tới thiết bị được quản lý. Nó được thực hiện để lấy ra một hoặc nhiều giá trị từ thiết bị được quản lý.
- GET NEXT: hoạt động tương tự như GET. Sự khác biệt đáng kể là thao tác GET NEXT lấy giá trị của OID kế tiếp trong cây MIB.
- GET BULK: thao tác GET BULK được sử dụng để lấy dữ liệu lớn từ bảng MIB.
- SET: thao tác này được manager sử dụng để sửa đổi hoặc chỉ định giá trị của thiết bị được quản lý.
<img src="https://www.manageengine.com/network-monitoring/images/snmp-get-response.gif">
- TRAPS: không giống như các lệnh trên được bắt đầu từ manager SNMP, TRAPS được khởi tạo bởi các agent. Đây là một tín hiệu cho manager SNMP của agent khi có một sự kiện mới.
<img src="https://www.manageengine.com/network-monitoring/images/snmp-trap.gif">
- INFORM: lệnh này tương tự như TRAPS do agent khởi xướng, ngoài ra INFORM bao gồm xác nhận manager SNMP khi nhận thông báo.
<img src="https://www.manageengine.com/network-monitoring/images/snmp-inform-acknowledgment.gif">
- RESPONSE: đây là lệnh được sử dụng để mang lại giá trị hoặc tín hiệu của các hành động theo chỉ thị của SNMP manager.
	Giao tiếp SNMP điển hình: là một phần của gói giao thức TCP/IP, các gói tin của SNMP được gói như là UDP và gói tin được gói và truyền bởi giao thức Internet. Hình sau sẽ minh họa cho mô hình 4 lớp do Department of Defense (DoD) phát triển:
<img src="https://www.manageengine.com/network-monitoring/images/snmp-layers.gif">
Mặc định SNMP sử dụng cổng 161 và TRAP/INFORM sử dụng cổng 162 để truyền tin.
##8, Các phiên bản của SNMP
Kể từ khi được tạo ra, SNMP đã trải qua các phiên bản nâng cấp. Tuy nhiên phiên bản SNMP v1 và v2c là những phiên bản được sử dụng nhiều nhất của SNMP. Phiên bản SNMP v3 gần đây được sử dụng vì nó được tích hợp nhiều công nghệ hơn so với các phiên bản cũ, nhưng vẫn không được sử dụng nhiều như 2 phiên bản kia.
- SNMP v1: đây là phiên bản đầu tiên của giao thức được định nghĩa trong RFCs 1155 and 1157
- SNMP v2c: Đây là giao thức đã sửa đổi, bao gồm các cải tiến của SNMP v1 trong các loại gói tin giao thức, đường vận chuyển, các yếu tố cấu trúc MIB nhưng sử dụng cấu trúc quản trị SNMP v1 hiện có. Nó được định nghĩa trong RFC 1901, RFC 1905, RFC 1906, RFC 2578.
- SNMP v3: là phiên bản mới và an toàn của SNMP. SNMP v3 cũng tạo điều kiện cấu hình từ xa các thực thể SNMP. nó được xác định bởi  RFC 1905, RFC 1906, RFC 3411, RFC 3412, RFC 3414, RFC 3415.
##9, Cấu trúc bản tin SNMP
SNMP chạy trên nền UDP. Cấu trúc của một bản tin SNMP bao gồm : version, community và data.
<img src="http://i.imgur.com/HZ0gq.jpg">
+ Version : v1 = 0, v2c = 1, v2u = 2, v3 = 3.

+ Phần Data trong bản tin SNMP gọi là PDU (Protocol Data Unit). SNMPv1 có 5 phương thức hoạt động tương ứng 5 loại PDU. Tuy nhiên chỉ có 2 loại định dạng bản tin là PDU và Trap-PDU; trong đó các bản tin Get, GetNext, Set, GetResponse có cùng định dạng là PDU, còn bản tin Trap có định dạng là Trap-PDU.
##10, Mô hình lab