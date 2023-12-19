# SOLID Principles
## 1. Single Responsibility Principle
**Một class chỉ có duy nhất một lý do để thay đổi**
Mục đích của principle này là để giảm độ phức tạp của phần mềm.

Trong ví dụ dưới, class `Employee` có lý do để thay đổi khi thay đổi vị trí công việc, nhưng khi thay đổi format của báo cáo thời gian làm việc thì cũng có thể dẫn đến nó thay đổi. Do đó chức năng in báo cáo sẽ được tách ra thành class `TimeSheetReport`

![Single Responsibility Principle](/out//00.diagrams/02.design-parterns/00.design-principles/single_responsibility/Single%20Responsibility%20Principle.png)

## 2. Open/Closed Principle
**Các class nên open cho extension nhưng closed với modification**
Mục đích của principle này là giữ cho code đang có không bị phá vỡ khi phát triển tính năng mới.

![Open/Closed Principle](/out//00.diagrams/02.design-parterns/00.design-principles/open_closed_responsibility/Open%20Closed%20Principle.png)

## 3. Liskov Substitution Principle
**Khi extend một class, cần đảm bảo có thể  pass object của subclass vào chỗ của superclass mà không phá vỡ hoạt động của phần code đang sử dụng object của superclass đó**

Cần đảm bảo các điều sau:
- Type của các parameter trong method của subclass nên tương đồng hoặc có tính abstract hơn type ở trong method của superclass. Ví dụ có một class có method là `feed(Cat c)`, khi muốn extend class trên thì subclass đó nên sử dụng `feed(Animal c)` thay vì `feed(BengalCat c)` vì `Animal` là superclass của `Cat` và nó mang tính bao quan hơn.
- Return type của method ở subclass nên tương đồng hoặc là *subtype* của của return type của method trong superclass. Ví dụ có một class có method là `buyCat() -> Cat` thì trong subclass của nó thì return type sẽ là `BengalCat` vì đó là subtype của `Cat`, và ta có method trong subclass là `buyCat() -> BengalCat`.
- Một method trong subclass không nên throw type exception một type nào khi mà method đó trong superclass không có throw type exception. Nói cách khác là tye exception ở subclass phải tương đồng hoặc là subtype của type exception ở superclass.
- Một subclass không nên làm tăng cường thêm các điều kiện đầu vào (pre-condition). Ví dụ ở superclass có một method có paremeter type là `int`, nghĩa là khi một nơi nào đó sử dụng method đó có thể đưa vào paremeter cả số âm và số dương đều được, do vậy ở subclass không nên overide method đó là throw exception nếu parameter đó là âm.
- Một subclass không nên làm yếu đi các điều kiện kết thúc (post-condition). Ví dụ ở superclass kết nối với database và đóng kết nối sau khi xử lý xong, thì ở subclass không nên overide để giữ lại kết nối với database mà không đóng.
- Một subclass không nên thay đổi giá trị của các private field trong superclass.

Ví dụ:

![Liskov Substitution Principle](/out//00.diagrams/02.design-parterns/00.design-principles/liskov_substitution/Liskov%20Substitution%20Principle.png)

## 4. Interface Segregation Principle
**Sử dụng interface vừa đủ sao cho các class implement interface không cần phải implement các method mà nó không cần**

Ví dụ:

![Interface Segregation Principle](/out//00.diagrams/02.design-parterns/00.design-principles/interface_segregation/Interface%20Segregation%20Principle.png)

## 5. Dependency Inversion Principle
**Các high-level class không nên phụ thuộc vào các low-level class. Cả hai nên phụ thuộc vào abstraction. Abstraction không nên phụ thuộc vào detail**


Ví dụ:

![Dependency Inversion Principle](/out//00.diagrams/02.design-parterns/00.design-principles/dependency_inversion/Dependency%20Inversion%20Principle.png)