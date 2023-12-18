# OOP
## Basic OOP
### 1. Class và object
Một ví dụ về một class và object

![Cat class example](/out//00.diagrams/01.basic-oop/class/BasicOOP%20Class.png)

### 2. Class hierachies (Kế thừa class)
Parrent class gọi là **superclass**, class con của nó gọi là **subclass**.Subclass kế thừa các attribute và method từ parent class của nó, nhưng định nghĩa các attribute khác. Như subclass của class Cat sẽ có method `meow`

Ví dụ về class Cat và Dog kế thừa từ class Animal
![Class hierachies example](/out//00.diagrams/01.basic-oop/class_hierachies/Class%20hierarchies.png)

## Tính chất của OOP
Có 4 tính chất chính là
### 1. Abstraction
*Abstraction* là một model cho một object thật trong thực tế hoặc một hiện tượng và giới hạn trong một context cụ thể.
Ví dụ như máy bay thì có thể là máy bay thật hoặc máy bay ảo, máy bay trong game.


### 2. Encapsulation
Để khởi động một chiếc xe, chúng ta chỉ cần mở khoá và nhấn nút khởi động. Chúng ta không cần phải kết nối bình xăng, đường xây điện, bộ đánh lửa....
Tất cả các quá trình này được thực hiện qua một **interface**, đó là một public part của một object để tương tác với các object khác.

*Encapsulation* là khả năng của một object để ẩn các trạng thái và hành động của nó khỏi các object khác, chỉ giao tiếp qua interface.

Ví dụ về class Cat và Dog kế thừa từ class Animal

![Encapsulation example](/out//00.diagrams/01.basic-oop/encapsulation/Encapsulation.png)

### 3. Inheritance
*Inheritance* là khả năng tạo một class mới dựa trên class đã có sẵn. Lợi điểm chính của inheritance là sử dụng lại code.

Ví dụ về class Cat từ class Animal và bao gồm 2 interface của class Animal là FourLegged và OxygenBreather

![Inheritance example](/out//00.diagrams/01.basic-oop/inheritance/Inheritance.png)

### 3. Polymorphism
Hầu hết các loài thú vật đề có thể tạo ra âm thanh, nhưng mỗi loài thì có một loại âm thanh khác nhau. Do đó chúng ta có thể đặt class Animal là `abstract` và các method trong nó cũng là `abstract` như sau:

![Polymorphism example](/out//00.diagrams/01.basic-oop/polymorphism/Polymorphism.png)
 

 ## Quan hệ giữa các object
 ### 1. Dependency
 *Dependency* là mối quan hệ cơ bản nhất và yếu nhất trong quan hệ giữa các object. Mối quan hệ này tạo ra việc khi một class có thay đổi thì class còn lại cũng sẽ thay đổi.
 Chúng ta có thể làm cho mối quan hệ dependency này yếu hơn bằng cách sử dụng các inteface hoặc các abstract class.

 Ví dụ về class `Professor` phụ thuộc vào `Course`

 ![Dependency example](/out//00.diagrams/01.basic-oop/dependency/Dependency.png)

 ### 2. Association
 *Association* là quan hệ khi một object sử dụng hay tương tác với một object khác.

Ví dụ về class `Professor` tương tác với `Student`

![Association example](/out//00.diagrams/01.basic-oop/association/Association.png)

```swift
class Professor:
    var student: Student

    func teach(course: Course) {
        self.student.remember(course.getKnowledge())
    }
```

### 3. Aggregation
*Aggregation* là một loại associtaion đặc biệt để biểu diễn mối quan hệ `one-to-many`, `many-to-many` hoặc `whole-part` giữa các object.
Các component có thể tồn tại mà không cần container hoặc có thể liên kết với nhiều container khác cùng một lúc.

Ví dụ về class `Professor` thuộc container `Department`, `Professor` có thể tồn tại mà không cần thuộc bất kỳ một `Department` nào hoặc thuộc nhiều `Department` cùng một lúc.

![Aggregation example](/out//00.diagrams/01.basic-oop/aggregation/Aggregation.png)

### 3. Composition
*Composition* là một loại aggregation đặc biệt. Các component chỉ có thể tồn tại khi container tồn tại.

Ví dụ class `Department` gắn với `University` và chỉ có thể tồn tại khi `University` tồn tại.

![Composition example](/out//00.diagrams/01.basic-oop/composition/Composition.png)
