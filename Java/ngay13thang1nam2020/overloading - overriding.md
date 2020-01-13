# OVERLOADING


**Overview about Overloading- (Tổng quan về overloading)**

Bài học về chồng chất phương thức - Overloading method
![](https://beginnersbook.com/wp-content/uploads/2013/05/constructor_overloading.jpg)


Trong Java, overloading được định nghĩa là nạp chồng phương thức, có nghĩa là nếu trong một lớp có nhiều phương thức cùng tên nhưng:
* Khách nhau về đối số truyền vào và các đối số có cùng kiểu dữ liệu
* Có cùng số đối số truyền vào và các đối số không có cùng kiểu dữ liệu. 
* Khác nhau trình tự kiểu dữ liệu của các đối số.

## To do - Cần làm gì để nạp chồng phương thức?
Thật ra rất đơn giản, chúng ta chỉ việc cần:
- Thay đổi kiểu dữ liệu của đối số
- Thay đổi tham số truyền vào của đối số.
- Thay đổi trình tự tham số truyền vào của đối số.

##  Ví dụ
* Thay đổi tham số truyền vào
-----------
>     package viduoverloading;
> 
>     public class PhepCongHaiSo {
>       public int add(int a, int b) {
>           return a + b;
>       }
>      
>       public int add(int a, int b, int c) {
>           return a + b + c;
>       }
>      
>     }
>     public class TestOverloading {
>      
>         public static void main(String[] args) {
>             PhepCongHaiSo test = new PhepCongHaiSo();
>             System.out.println("Tổng = " + test.add(11, 12));
>             System.out.println("Tổng = " + test.add(11, 12, 13));
>         }
>      
>     }
-----------

- Lưu ý:
  - Thay đổi số lượng tham số truyền vào
  - Thay đổi kiểu tham số truyền vào
  - Không có ý nghĩa nếu ta thay đổi chỉ là tên của tham số.

-----------
>     package viduoverloading;
> 
>     public class PhepCongHaiSo {
>       public string add(string a) {
>           return a;
>       }
>      
>       public string add(string b) {
>           return b;
>       }
>      
>     } 
-----------
**Code ở trên không có ý nghĩa, nó sẽ báo lỗi**

*Mô tả ví dụ: Với ví dụ trên ta có 2 phương thức `add(int a, int b) và add(int a, int b, int c)` nó có đặc điểm là cùng tên và khác nhau về tham số. Cụ thể phương thức đầu tiên có 2 tham số a và b và phương thức thứ 2 có 3 đối số a,b và c. Đây là trường hợp đầu tiên*.

* Thay đổi kiểu dữ liệu của đối số truyền vào
-----------
>     package viduoverloading;
> 
>     public class PhepCongHaiSo {
>       public int add(int a, int b) {
>           return a + b;
>       }
>      
>       public int add(float a, float b) {
>           return a + b + c;
>       }
>      
>     }
>     public class TestOverloading {
>      
>         public static void main(String[] args) {
>             PhepCongHaiSo test = new PhepCongHaiSo();
>             System.out.println("Tổng = " + test.add(11, 12));
>             System.out.println("Tổng = " + test.add(11.0, 12.0));
>         }
>      
>     }
-----------
*Mô tả ví dụ: Với ví dụ trên ta có 2 phương thức `add(int a, int b) và add(float a, float b)` nó có đặc điểm là cùng tên và khác nhau về kiểu dữ liệu của tham số. Cụ thể phương thức đầu tiên có 2 tham số a và b có kiểu dữ liệu `int` và phương thức thứ 2 cũng có 2 đối số a và b có kiểu dữ liệu `float`. Đây là trường hợp thứ 2*.


* Thay đổi trình tự tham số
-----------
>     package viduoverloading;
> 
>     public class PhepCongHaiSo {
>       public string print(int a, string b) {
>           //...
>       }
>      
>       public string print(string a, int b) {
>           //...
>       }
>     }
-----------
*Mô tả ví dụ: Với ví dụ trên ta có 2 phương thức `print(int a, char b) và print(char a, int b)` nó có đặc điểm là khác nhau về trình tự được truyền vào của các tham số. Cụ thể phương thức đầu tiên có 2 tham số a và b có kiểu dữ liệu lần lượt là `int` và `string` và phương thức thứ 2 có 2 tham số a và b có kiểu dữ liệu lần lượt là `string` và `int`. Đây là trường hợp thứ 3*.







# OVERRIDING
**Overview about Overriding- (Tổng quan về Overriding)**
Bài học về ghi đè phương thức - Overriding method

![](https://codebridgeplus.com/public/wp-content/uploads/method-overriding-in-java.png)


Khái quát: Trong Java, overriding được định nghĩa là ghi đè phương thức, có nghĩa là khi một lớp con kế thừa trực tiếp từ một lớp cha thì lớp con đó có thể định nghĩa lại một phương thức đã có trong lớp cha cho phù hợp với mục đích của nó.

## Quy tắc ghi đè phương thức
1. Danh sách các đối số phải giống với phương thức được ghi đè.
2. Kiểu trả về phải giống với kiểu trả về được khai báo trong phương thức được ghi đè của lớp cha.
3. Mức truy cập của phương thức ghi đè phương thức ở lớp cha không được nhỏ hơn phương thức đó trong lớp cha. Ví dụ: phương thức trong lớp cha được khai báo là public thì phương thức ghi đè phương thức đó trong lớp con không thể có phạm vi truy cập là private hoặc protected.
4. Một phương thức được khai báo là final hoặc static thì phương thức không thể được ghi đè.
5. Các hàm tạo của lớp cha không thể được ghi đè.


##  Ví dụ
*file:* vd1.java
```
package viduoverriding;
 
public class Superclass {
     
    public void hienThi() {
        System.out.println("Đây là phương thức hiển thị của lớp cha Superclass.");
    }
     
}
public class Subclass extends Superclass {
 
    @Override
    public void hienThi() {
        System.out.println("Đây là phương thức hiển thị của lớp con Subclass.");
    }
 
}
public class TestOverriding {
     
    public static void main(String[] args) {
        // khai báo đối tượng của lớp Superclass
        Superclass superclass = new Superclass();
         
        // khai báo đối tượng có bản chất là Superclass
        // nhưng đóng vai trò là 1 Subclass
        // vì vậy sẽ chạy những hàm của Subclass
        Superclass subclass = new Subclass();
         
        // gọi phương thức hienThi() của lớp cha
        superclass.hienThi();
         
        // gọi phương thức hienThi() của lớp con
        subclass.hienThi();
    }
     
}
```

Note: 
```
Đây là toàn bộ kiến thức cơ bản về Overriding và Overloading. 
Đây là 2 khái niệm hết sức quan trọng và được sử dụng rất nhiều xuyên suốt các quá trình lập trình Java.
```
