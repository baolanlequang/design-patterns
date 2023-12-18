# SOLID Principles
## 1. Single Responsibility Principle
**Một class chỉ có duy nhất một lý do để thay đổi**
Mục đích của principle này là để giảm độ phức tạp của phần mềm.

Trong ví dụ dưới, class `Employee` có lý do để thay đổi khi thay đổi vị trí công việc, nhưng khi thay đổi format của báo cáo thời gian làm việc thì cũng có thể dẫn đến nó thay đổi. Do đó chức năng in báo cáo sẽ được tách ra thành class `TimeSheetReport`

![Single Responsibility Principle](/out//00.diagrams/02.design-parterns/00.design-principles/single_responsibility/Single%20Responsibility%20Principle.png)

## 2. Open/Closed Principle
**Các class nên open cho extension nhưng closed với modification**
Mục đích của principle này là giữ cho code đang có không bị phá vỡ khi phát triển tính năng mới.

![ Open/Closed Principle](/out//00.diagrams/02.design-parterns/00.design-principles/open_closed_responsibility/Open%20Closed%20Principle.png)