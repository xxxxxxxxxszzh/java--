### 实验名称： Java 类继承与权限控制设计

#### 1. 实验目的：
- 掌握类的继承机制，利用继承关系简化代码并增加代码复用性。
- 了解和使用`super()`来调用父类的构造方法。
- 理解Java的不同访问修饰符，及其对类属性和方法可见性的影响。

#### 2. 设计思路：
本次实验将先前设计的类重新进行架构。识别了学生和教师之间的共同性，并决定创建一个通用的`Person`类。此外，利用继承机制，使得`Student`和`Teacher`类继承自`Person`类。课程将与教师关联，而学生将选择这些课程。

#### 3. 类的设计：
- **3.1 Course类**
  - **Attributes:**
    - `id`: 课程ID。
    - `courseName`: 课程名。
    - `location`: 上课地点。
    - `time`: 上课时间。
    - `teacher`: 授课教师。
  - **Methods:**
    - Getter and Setter方法。

- **3.2 Person类（父类）**
  - 这是`Student`和`Teacher`的父类，包含共同的属性。
  - **Attributes:**
    - `id`: 人员ID（protected，子类可见）。
    - `name`: 姓名。
    - `gender`: 性别。
  - **Methods:**
    - Getter方法。
    - 构造方法：使用传入的参数来初始化属性。

- **3.3 Student类（子类）**
  - 该类继承自`Person`类，并有其特定的属性和方法。
  - **Attributes:**
    - `selectedCourses`: 已选课程列表。
  - **Methods:**
    - `addSelectedCourse(Course course)`: 添加已选课程。
    - `getSelectedCourses()`: 获取所有已选课程。
    - 构造方法：使用`super()`调用父类构造方法，并初始化特有的属性。

- **3.4 Teacher类（子类）**
  - 与`Student`类类似，但有所教课程的属性和方法。
  - **Attributes:**
    - `teachingCourses`: 所教课程列表。
  - **Methods:**
    - `addTeachingCourse(Course course)`: 添加所教课程。
    - `getTeachingCourses()`: 获取所有所教课程。
    - 构造方法：使用`super()`调用父类构造方法，并初始化特有的属性。

#### 4. 实验内容与步骤：
1. 设计基础的`Person`父类，并定义共有的属性和方法。
2. 创建`Student`和`Teacher`子类，这两个类都应继承`Person`类。
3. 在子类的构造方法中使用`super()`来调用父类的构造方法，确保所有属性都被正确初始化。
4. 使用不同的Java包来存储基础类和测试类，以验证权限访问控制。
5. 在测试类中，模拟学生选课和教师授课的场景，以及验证继承后属性和方法的可见性。

#### 5. 实验结果：
- 通过测试类的输出，验证了：
  - 学生可以选择课程。
  - 教师可以有所教的课程。
  - 继承关系正确实施，并且子类可以访问父类的`protected`属性。
  - `super()`在子类的构造方法中正确使用，确保了属性的正确初始化。

#### 6.输出：
---
学生编号：1001
学生姓名：李四
---

- 课程名称：Java编程
- 上课地点：教学楼A201
- 上课时间：周三 3-5节
- 授课教师：张三

---

- 课程名称：Python编程
- 上课地点：教学楼B202
- 上课时间：周四 4-6节
- 授课教师：李华

---
学生编号：1002
学生姓名：王五
---
- 课程名称：Java编程
- 上课地点：教学楼A201
- 上课时间：周三 3-5节
- 授课教师：张三

---

- 课程名称：Web开发
- 上课地点：教学楼C203
- 上课时间：周五 5-7节
- 授课教师：张三

---
#### 6. 实验总结：
深入理解Java的继承机制和权限访问控制。学习了如何有效地利用继承来简化代码和提高代码的复用性。同时，也探讨了Java中不同的访问修饰符，以及如何使用它们来控制属性和方法的可见性。
