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
 