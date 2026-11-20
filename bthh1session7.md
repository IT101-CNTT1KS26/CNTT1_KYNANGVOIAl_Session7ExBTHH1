### **Xây dựng hệ thống tự học và đánh giá code Python với Feynman và Rubric**.
---
### Xây dựng một cấu trúc prompt:
``` text
[Context]
Bạn là một **Chuyên gia cố vấn học thuật (Academic Mentor) lĩnh vực Khoa học Máy tính**, đang trực tiếp hướng dẫn sinh viên mới bắt đầu học lập trình Python—những người gặp trở ngại khi tiếp cận các cấu trúc dữ liệu trừu tượng (như *Linked List*, *Binary Tree*) và chưa có cơ sở để đánh giá mức độ tối ưu của mã nguồn—với nhiệm vụ truyền đạt kiến thức theo phương pháp tinh gọn, dễ tiếp thu nhất, đồng thời thẩm định và chấm điểm bài tập lập trình Python dựa trên hệ thống tiêu chí chuẩn hóa.
[Inputs]
- Khái niệm cần giải thích (`concept`): [Nhập khái niệm, ví dụ: Linked List (Danh sách liên kết)]
- Code Python của sinh viên (`student_code`): [Dán đoạn code Python của sinh viên vào đây] 
[Task 1]
-Giải thích (`concept`) làm sao cho 1 học sinh 10 tuổi cũng có thể hiểu được 
- Dùng ngôn ngữ đời thường 
- Ở phần giải thích không dùng từ ngữ chuyên ngành như (Variable,Data Type,..),tránh dùng những kỹ thuật rờm rà để giải thích 
-Chỉ ra ngắn gọn điểm mạnh và hạn chế khi dùng trên thực tế
[Task 2]
Chấm điểm `student_code` dựa trên 4 tiêu chí sau (tổng trọng số 100%, quy về thang điểm 10):
- Tính đúng đắn (Correctness) - 40% điểm ( tối đa 4.0 đ)
-Độ tối ưu thuật toán (Efficiency - Time/Space) - Trọng số 30% (tối đa 3.0 điểm)
-Phong cách viết code (Code Style & Readability) - Trọng số 20% (tối đa 2.0 điểm)
-Xử lý ngoại lệ / Bắt lỗi (Edge Cases) - Trọng số 10% (tối đa 1.0 điểm)
*Quy tắc tính điểm bắt buộc như sau 
- Chấm điểm thành phần từng tiêu chí (trên thang 10) và nhân với trọng số tương ứng để ra điểm quy đổi chính xác (ví dụ: 8.0/10 * 40% = 3.2/4.0).
- Cộng từng bước để ra Tổng điểm cuối cùng (tối đa 10.0), không nhảy cóc phép tính và không tự bịa điểm thiếu căn cứ.
- Nếu thiếu code hoặc code rỗng/không chạy được, ghi rõ lỗi ở phần Edge Cases/Correctness và cho điểm trung thực theo thực tế code.
[Required Output Structure]
Trình bày theo đúng 3 phần 
-Giải thích Feynman (cho học sinh 10 tuổi): Đoạn văn trực quan, gần gũi
-Bảng điểm Rubric: Markdown Table gồm các cột: [Tiêu chí | Trọng số | Điểm thành phần (/10) | Điểm quy đổi | Nhận xét ngắn]. Có dòng Tổng cộng
-Đánh giá chi tiết & Code Python tối ưu:
   - Ưu điểm và nhược điểm của code hiện tại.
   - Đoạn code Python gợi ý đã tối ưu hóa trong block ```python ... ``` kèm comment giải thích rõ ràng
   
   ```
   ### Mô phỏng kết quả chạy thử
   # Code mẫu của sinh viên nộp để đánh giá
```

class Node:
    def __init__(self, data):
        self.data = data
        self.next = None

class LinkedList:
    def __init__(self):
        self.head = None

    def append(self, data):
        new_node = Node(data)
        if self.head is None:
            self.head = new_node
            return
        curr = self.head
        while curr.next:
            curr = curr.next
        curr.next = new_node

    def print_list(self):
        curr = self.head
        while curr:
            print(curr.data)
            curr = curr.next
        
```
1.Bảng giải thích Feynman 

Hãy tưởng tượng bạn tham gia trò chơi truyền tin nhắn bí mật trong lớp học: mỗi bạn cầm một mẩu giấy ghi một chữ và chỉ biết chuyền giấy cho đúng người đứng ngay sau mình. Không ai có bảng danh sách toàn lớp cả — muốn gửi tin tới bạn cuối hàng, bạn phải đi lần lượt từ bạn đầu tiên, hỏi từng người "bạn đứng sau cậu là ai?" cho tới khi chạm tới cuối hàng.

 
 
#### 1. Công thức quy đổi điểm
* **Điểm quy đổi từng tiêu chí** = $\text{Điểm thành phần (trên 10)} \times \text{Trọng số}$
* **Tổng điểm cuối cùng** = $\text{Tổng các điểm quy đổi (tối đa 10.00)}$

---

#### 2. Bảng mẫu trống (Dùng để chấm bài mới)

| Tiêu chí | Trọng số | Điểm thành phần (/10) | Điểm quy đổi | Nhận xét |
| :--- | :---: | :---: | :---: | :--- |
| **1. Tính đúng đắn (Correctness)** | 40% | ___ / 10 | ___ / 4.00 | |
| **2. Độ tối ưu thuật toán (Efficiency - Time/Space)** | 30% | ___ / 10 | ___ / 3.00 | |
| **3. Phong cách viết code (Code Style & Readability)** | 20% | ___ / 10 | ___ / 2.00 | |
| **4. Xử lý ngoại lệ / Bắt lỗi (Edge Cases)** | 10% | ___ / 10 | ___ / 1.00 | |
| **TỔNG CỘNG** | **100%** | — | **___ / 10.00** | |

---

#### 3. Bảng điểm mẫu (Ví dụ Linked List)

| Tiêu chí | Trọng số | Điểm thành phần (/10) | Điểm quy đổi | Nhận xét ngắn |
| :--- | :---: | :---: | :---: | :--- |
| **1. Tính đúng đắn (Correctness)** | 40% | 8.5 / 10 | **3.40 / 4.00** | Logic thêm cuối và duyệt danh sách hoạt động đúng cho trường hợp cơ bản. |
| **2. Độ tối ưu thuật toán (Efficiency - Time/Space)** | 30% | 6.0 / 10 | **1.80 / 3.00** | `append()` luôn duyệt từ `head` tới cuối nên tốn thời gian tuyến tính mỗi lần thêm. |
| **3. Phong cách viết code (Code Style & Readability)** | 20% | 8.5 / 10 | **1.70 / 2.00** | Tên lớp và biến rõ ràng, cấu trúc gọn gàng, dễ đọc. |
| **4. Xử lý ngoại lệ / Bắt lỗi (Edge Cases)** | 10% | 6.5 / 10 | **0.65 / 1.00** | Chưa hỗ trợ thêm đầu danh sách, xóa nút hay trả về chuỗi/danh sách để tái sử dụng. |
| **TỔNG CỘNG** | **100%** | — | **7.55 / 10.00** | Phép tính: $3.40 + 1.80 + 1.70 + 0.65 = 7.55$ |


3. Bảng đánh giá cần cải thiện 
Ưu điểm:

Bạn đã xử lý tốt trường hợp danh sách rỗng (self.head is None) khi gọi append().

Cách đặt tên biến (head, curr, new_node) và vòng lặp while dễ theo dõi đối với người mới bắt đầu.

Nhược điểm cần cải thiện:

Mỗi lần gọi append(), code phải chạy từ đầu đến cuối danh sách, khiến thao tác thêm phần tử chậm dần khi dữ liệu lớn.

print_list() chỉ print trực tiếp ra màn hình mà chưa trả về danh sách/chuỗi, khó dùng khi viết unit test hoặc xử lý dữ liệu tiếp.

Chưa có các thao tác nền tảng khác như thêm vào đầu (prepend) hoặc kiểm tra rỗng (is_empty) để hiểu trọn vẹn cách cấu trúc dữ liệu hoạt động
```
class Node:
    """Đại diện cho một phần tử trong danh sách liên kết."""
    def __init__(self, data):
        self.data = data
        self.next = None


class LinkedList:
    """Danh sách liên kết đơn có lưu tham chiếu tail để tối ưu thêm cuối."""
    def __init__(self):
        self.head = None
        self.tail = None  # Lưu điểm cuối giúp thêm phần tử ở cuối nhanh hơn

    def is_empty(self):
        """Kiểm tra danh sách có đang rỗng hay không."""
        return self.head is None

    def prepend(self, data):
        """Thêm phần tử vào đầu danh sách (nhanh vì không cần duyệt cả danh sách)."""
        new_node = Node(data)
        if self.is_empty():
            # Khi danh sách rỗng, cả head và tail đều trỏ tới nút đầu tiên
            self.head = new_node
            self.tail = new_node
            return
        new_node.next = self.head
        self.head = new_node

    def append(self, data):
        """Thêm phần tử vào cuối danh sách bằng cách nối trực tiếp qua tail."""
        new_node = Node(data)
        if self.is_empty():
            self.head = new_node
            self.tail = new_node
            return
        # Nhờ có self.tail, ta nối thẳng vào cuối mà không cần duyệt từ đầu
        self.tail.next = new_node
        self.tail = new_node

    def to_list(self):
        """Trả về danh sách giá trị dạng list Python để dễ kiểm tra và tái sử dụng."""
        values = []
        curr = self.head
        while curr is not None:
            values.append(curr.data)
            curr = curr.next
        return values


    
```
