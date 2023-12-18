# Design Principles
## Encpsulate what varies (đóng gói các phần khác nhau)
Xác định các phần khác nhau trong ứng dụng và phân chia chúng vào một chỗ tương tự nhau.

### 1. Encapsulation on a method level (đóng gói ở tầng method)
Giả sử có hàm tính tổng hoá đơn như sau:

```swift
func getOrderTotal(order) -> Double {
  total = 0
  for item in order.lineItems {
    total += item.price * item.quantity
  }

  if (order.country == "US") {
    total += total * 0.07 // US sales tax
  }
  else if (order.country == "EU") {
    total += total * 0.20 // European VAT
  }

  return total
```

Sau khi tách phần lấy tax rate ra ta có được
```swift
func getTaxRate(country) -> Double {
  if (oder.country == "US") {
    return 0.07 // US sales tax
  }
  else if (oder.country == "EU") {
    return 0.20 // European VAT
  }
  return 0.0
}

func getOrderTotal(order) -> Double {
  total = 0
  for item in order.lineItems {
    total += item.price * item.quantity
  }

  total += total * getTaxRate(order.country)

  return total
```

### 2. Encapsulation on a class level (đóng gói ở tầng class)
Trước khi tách

![Before encapsulation class](/out//00.diagrams/02.design-parterns//00.design-principles/before_encapsulation_class_level/Before%20Encapsulation%20Class%20Level.png)

Sau khi tách

![After encapsulation class](/out//00.diagrams/02.design-parterns//00.design-principles/after_encapsulation_class_level/After%20Encapsulation%20Class%20Level.png)


## Program to an Interface, not an Implementation
Lập trình tương tác đến một interface, chứ không phải là một implementation cụ thể. Tạo sự phụ thuộc vào abstraction class thay vì một concrete class.

Ví dụ về class Cat và Company

![Program to an Interface](/out//00.diagrams/02.design-parterns/00.design-principles/program_to_interface/Program%20to%20an%20Interface.png)


### 3. Favor Composition over Inheritance (ưu tiên composition hơn là inheritance)
Các vấn đề của inheritance
* Một subcalss không thể cắt giảm interface của superclass => phải implement hết tất cả các interface của superclass
* Khi overriding các method cần phải đảm bảo hoạt động mới phải tương thích với base method.
* Inheritance phá vỡ encapsulation của superclass bởi vì chi tiết của superclass có ở subclass.
* Subclass gắn hc8at5 với superclass. Bất kỳ thay đổi nào của superclass cũng có thể phá vỡ hoạt động của subclass.
* Sử dụng lại code thông qua inheritance có thể hiện tượng parallel inheritance.

Ví dụ về vấn đề inheritance

![Inheritance](/out//00.diagrams/02.design-parterns/00.design-principles/inheritance/Inheritance.png)

Chuyển sang sử dụng composition và aggregation

![Composition](/out//00.diagrams/02.design-parterns/00.design-principles/composition/Composition.png)