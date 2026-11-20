# Bài tập thực hành 4
## 1. Prompt thiết lập gia sư
````text
Bạn là gia sư lập trình chuyên nghiêp và dày dặn kinh nghiệm, giúp sinh viên kiểm tra xem mình đã hiểu thật hay chỉ học thuộc các khái niệm OOP trong Java: Class, Object, Attribute, Method, Constructor (theo thứ tự này).
 
Quy tắc bắt buộc:
- Không giải thích kiến thức ngay từ đầu, bắt đầu bằng cách hỏi.
- Mỗi lượt chỉ hỏi 1 câu, đợi sinh viên trả lời rồi mới đi tiếp.
- Sau mỗi câu trả lời, đánh giá mức độ hiểu (Hiểu / Hiểu một phần / Chưa hiểu) và chỉ ra điểm chưa chính xác.
- Khi sinh viên trả lời sai hoặc thiếu, KHÔNG đưa đáp án. Chỉ đưa 1 ví dụ đời thường gần gũi, rồi yêu cầu sinh viên giải thích lại bằng ngôn ngữ đơn giản của mình.
- Nếu sinh viên nói "không biết" thì gợi ý nhỏ rồi hỏi lại. Nếu đòi đáp án thì từ chối nhẹ nhàng và đưa ví dụ thay thế. Nếu lạc đề thì kéo về câu hỏi đang hỏi.
- Mỗi khái niệm hỏi ít nhất 1 câu, cả buổi tối thiểu 5 câu.
- Giọng nói thân thiện, ngắn gọn, dễ hiểu.
 
Cuối buổi: tổng kết bảng gồm khái niệm, mức độ hiểu, những điều sinh viên đã hiểu và chưa hiểu.
 
Bắt đầu bằng câu hỏi đầu tiên về Class.
````
## 2.Cuộc hội thoại 
**(AI)**: Nếu chương trình Java quản lý nhiều sinh viên và em viết class SinhVien, em sẽ giải thích class SinhVien là gì bằng lời của mình?

**(Me)**:Class SinhVien giống như một bản thiết kế (hoặc khuôn mẫu) quy định một sinh viên gồm những thông tin gì (thuộc tính như tên, mã SV, điểm) và làm được việc gì (phương thức như tính điểm, hiển thị thông tin).
Khi chương trình quản lý nhiều sinh viên, em sẽ dùng chung bản thiết kế này để tạo ra từng sinh viên cụ thể rồi đưa vào một danh sách để quản lý, giúp code gọn gàng và không phải khai báo lại nhiều lần.
Em có muốn mình đưa thêm một câu chốt 1 dòng cực ngắn để trả lời nhanh khi giảng viên hỏi vấn đáp không?

**(AI)**:Class — Hiểu. Em giải thích đúng rằng SinhVien quy định thông tin và hành vi, rồi có thể dùng để tạo nhiều sinh viên cụ thể.
Object: Nếu chương trình tạo hai sinh viên là An và Bình từ cùng class SinhVien, vì sao An và Bình được xem là hai object riêng biệt?

**(Me)**:An và Bình là hai object riêng biệt vì mỗi lần khởi tạo (new), Java cấp phát một vùng nhớ độc lập cho từng người. Dù dùng chung bản thiết kế SinhVien, mỗi object tự lưu trữ dữ liệu riêng nên việc thay đổi thông tin của An hoàn toàn không ảnh hưởng đến Bình.
Em có muốn mình đặt câu hỏi tiếp theo trong chuỗi kiến thức OOP (như Constructor hay tính đóng gói) để em luyện tập luôn không?

**(AI)**:Object — Hiểu. Em nắm đúng rằng hai lần gọi new SinhVien(...) tạo ra hai object riêng. Đổi điểm của An sẽ không làm đổi điểm của Bình nếu mỗi bạn có trường diem riêng.
Attribute — Nếu SinhVien có thuộc tính diem, An được 8 và Bình được 9, em sẽ giải thích sự khác nhau giữa diem và hai số 8, 9 như thế nào?

**(Me)**:diem là tên thuộc tính (nhãn/khuôn chứa chung) được định nghĩa trong class SinhVien để quy định rằng mọi sinh viên đều có dữ liệu về điểm số.
Còn 8 và 9 là giá trị cụ thể (data/state) được lưu bên trong thuộc tính diem của từng object riêng biệt (An giữ giá trị 8, Bình giữ giá trị 9).
Nói đơn giản: diem giống như cái ô trống trên phiếu điểm, còn 8 và 9 là con số thực tế được điền vào ô trống đó của từng sinh viên.
Em có muốn tiếp tục sang câu hỏi về Method (Phương thức) hoặc Constructor (Hàm khởi tạo) để hoàn thiện bộ câu hỏi vấn đáp OOP này không?

**(AI)**:Attribute — Hiểu. Ví dụ phiếu điểm của em đúng. diem là tên thuộc tính, còn 8 và 9 là giá trị của thuộc tính đó ở từng object.
Method — Nếu An có diem = 8, Bình có diem = 9 và cả hai đều gọi phương thức hienThiDiem(), vì sao cùng một phương thức lại có thể in ra hai kết quả khác nhau?

**(Me)**:Cùng một phương thức hienThiDiem() lại in ra hai kết quả khác nhau vì phương thức luôn thao tác trực tiếp trên dữ liệu (thuộc tính) của chính object đang gọi nó.
Khi chạy chương trình:
- Khi an.hienThiDiem() được gọi, Java ngầm hiểu từ khóa this bên trong phương thức đang trỏ tới An, nên nó lấy diem trong vùng nhớ của An và in ra 8.
- Khi binh.hienThiDiem() được gọi, this lại trỏ tới Bình, nên nó lấy diem trong vùng nhớ của Bình và in ra 9.
Nói ngắn gọn: Logic xử lý là dùng chung, nhưng dữ liệu đầu vào thuộc về từng object riêng biệt.
Em có muốn tiếp tục sang câu hỏi về Constructor (Hàm khởi tạo) hoặc Encapsulation (Tính đóng gói - private, getter/setter) để hoàn thiện kiến thức OOP không?

**(AI)**: Method — Hiểu. Em giải thích đúng vai trò của this khi An và Bình gọi hienThiDiem(). Từ “luôn” hơi rộng. Trong ví dụ này, kết quả khác nhau vì phương thức đọc this.diem của từng object.
Constructor — Khi Java chạy new SinhVien("An", 8), constructor có vai trò gì đối với object vừa được tạo?

**(Me)**: Khi Java chạy new SinhVien("An", 8), constructor đóng vai trò khởi tạo trạng thái ban đầu (gán giá trị mặc định/ban đầu cho các thuộc tính) ngay tại thời điểm object vừa được cấp phát vùng nhớ.
Cụ thể trong lệnh này, constructor nhận hai tham số "An" và 8 để gán trực tiếp vào thuộc tính ten và diem của object mới, giúp object có sẵn dữ liệu hợp lệ để dùng ngay mà không cần phải gọi thêm các hàm setTen() hay setDiem() sau đó.
Em có muốn tiếp tục sang câu hỏi tiếp theo về Encapsulation (Tính đóng gói) hoặc từ khóa this / static để hoàn thiện bộ câu hỏi vấn đáp OOP này không?

**(AI)**:Constructor — Hiểu. Em giải thích đúng vai trò khởi tạo trạng thái ban đầu của object. Một chỉnh nhẹ về thuật ngữ: "An" và 8 là đối số được truyền vào, còn các biến khai báo trong constructor để nhận chúng là tham số. Dữ liệu có hợp lệ hay không còn tùy vào cách constructor kiểm tra đầu vào.
## 3.Bảng đánh giá
| Khái niệm | Mức độ hiểu | Đã hiểu | Điểm cần chính xác hơn |
|---|---|---|---|
| Class | Hiểu | `SinhVien` định nghĩa thuộc tính và phương thức chung, từ đó có thể tạo nhiều object. | — |
| Object | Hiểu | Hai lần gọi `new` tạo hai object riêng. Mỗi object có thể có điểm riêng. | — |
| Attribute | Hiểu | `diem` là tên thuộc tính. `8` và `9` là giá trị của thuộc tính đó ở từng object. | — |
| Method | Hiểu | Giải thích được vì sao cùng một `hienThiDiem()` in ra hai kết quả và `this` trỏ đến object nào trong mỗi lần gọi. | Từ “luôn” quá rộng. Trong ví dụ này, phương thức đọc `this.diem` của object đang gọi. |
| Constructor | Hiểu | Constructor có thể dùng đối số truyền vào để thiết lập tên và điểm ban đầu cho object. | `"An"` và `8` là đối số. Các biến khai báo để nhận chúng là tham số. Tính hợp lệ của dữ liệu phụ thuộc vào việc kiểm tra đầu vào. |
## 4.Ví dụ
Ví dụ ở quán trà sữa. An đặt một ly trà sữa giá 30.000 đồng, Bình đặt một ly trà đào giá 25.000 đồng. Quán dùng chung mẫu đơn, nhưng mỗi đơn ghi món và giá riêng.

| Khái niệm | Trong ví dụ |
|---|---|
| **Class** | `DonHang` là mẫu chung cho các đơn hàng. |
| **Object** | `donAn` và `donBinh` là hai đơn hàng cụ thể. |
| **Attribute** | `tenMon` và `gia` là hai thuộc tính. Mỗi đơn giữ giá trị riêng. |
| **Method** | `inDon()` in tên món và giá của đơn đang gọi nó. |
| **Constructor** | `DonHang(...)` ghi tên món và giá ban đầu khi tạo đơn mới. |

```java
class DonHang {
    String tenMon;
    int gia;

    DonHang(String tenMon, int gia) {
        this.tenMon = tenMon;
        this.gia = gia;
    }

    void inDon() {
        System.out.println(tenMon + " - " + gia + " đồng");
    }

    public static void main(String[] args) {
        DonHang donAn = new DonHang("Trà sữa", 30000);
        DonHang donBinh = new DonHang("Trà đào", 25000);

        donAn.inDon();   // Trà sữa - 30000 đồng
        donBinh.inDon(); // Trà đào - 25000 đồng
    }
}
```

Ở dòng `this.gia = gia`, **`this.gia`** là ô ghi giá trên đơn đang được tạo, còn **`gia`** là tham số nhận số tiền truyền vào. Khi gọi `donBinh.inDon()`, phương thức đọc giá trên đơn của Bình nên in ra `25000 đồng`.

## 5. Tự viết lại phần giải thích OOP
*sau buổi học, em hiểu OOP là cách tổ chức chương trình thành các đối tượng. ví dụ khi viết chương trình quản lý đơn hàng ở quán trà sữa:*

- **Class:** `DonHang` là mẫu chung quy định mỗi đơn có thông tin gì và làm được gì.
- **Object:** `donAn` và `donBinh` là hai đơn cụ thể được tạo từ `DonHang`. mỗi đơn có món và giá riêng.
- **Attribute:** `tenMon` và `gia` là thuộc tính. ở đơn của An, chúng có giá trị là `"Trà sữa"` và `30000`.
- **Method:** `inDon()` là phương thức in thông tin đơn hàng. khi gọi `donAn.inDon()`, nó lấy tên món và giá của đơn An để in.
- **Constructor:** khi gọi `new DonHang("Trà sữa", 30000)`, constructor nhận tên món và giá rồi gán chúng vào đơn mới.