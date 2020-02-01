# OOPReview

// 4 tính chất của hướng đối tượng (có ví dụ và lợi ích khi sử dụng)
Nguồn tham khảo: https://viblo.asia/p/4-dac-tinh-cua-lap-trinh-huong-doi-tuong-object-oriented-program-XL6lAA7Nlek
1.	Tính kế thừa: 
Ví dụ: 
public class Flower(){
String color;
String name;

public void setColor(String color){
		this.color= color;
}

public String getColor(){
	return color;
}

public void setName(String name){
		this.name= name;
}

public String getName(){
	return name;
}

public Flower(){}

public Flower(String name, String color){
this.name=name;
this.color=color;
}
public String toString(){

System.out.println(this.name + “has ” +this.color+ ”color”);

}
}

public class Rose extends Flower(){

public Rose(String name, String color){
super(name,color);

}
public void display(){

System.out.println(toString());

}}
Như ví dụ ở trên, lớp Rose kế thừa lớp Flower. Bởi vì lớp Rose nó cũng có các thuộc tính như là name, color. Vì vậy nó không cần phải tạo ra thêm các thuộc tính đó lần nữa, thay vào đó chỉ cần kế thừa từ lớp cha có sẵn.
2.	Tính trừu tượng:
Ví dụ:
abstract class Animals(){
abstract void run();
}

class Dog extends Animals(){
		void run(){
		System.out.println(“running danger”);
}

public static void main(String args[]) {  
        Animals ani = new Dog();  
        ani.run();  
    }
}

Có thể linh động các method. giống như một class thông thường.
Các class extend có thể override hoặc không override các method thường.
Ở lớp cha Animals có phương thức abstract là run() và không có thân phương thức. Gọi phương thức run() ở  lớp Dog và triển khai nó ra.
3.	Tính đa hình:
Ví dụ:
public class Animals {
    public void show() {
        System.out.println("Đây là phương thức show() của lớp Animals");
    }
}

public class Cat extends Animals {
    public void show() {
        System.out.println("Đây là phương thức show() của lớp Cat");
    }
}

public class Main {
    public static void main(String[] args) {
        Animasl ani = new Animals();
        ani.show();  
// bản chất của Animals là Animals, nhưng vì khai báo Cat  nên chúng ta chỉ nhìn thấy những gì mà Cat có
        // vì vậy sẽ chạy những hàm của Cat
        ani = new Cat();
        ani.show();  
             }
}
4.	Tính đóng gói:
Ví dụ:
public class HinhChuNhat {
    private int rong; 
    private int dai; 
    
    public void setRong(int rong){
        this.rong = rong;
    }
    public void setDai(int dai){
        this.dai = dai;
    }
    public int getRong(){
        return this.rong;
    }
    public int getDai(){
        return this.dai;
    }
}
public class Main {
 
    public static void main(String[] args) {
        HinhChuNhat  HCN = new HinhChuNhat();
        HCN.setRong(3);
        HCN.setDai(4);
        System.out.println("HCN co chieu rong: " + HCN.getRong() );
        System.out.println("HCN co chieu dai: " + HCN.getDai() );
    }
};

Thông qua các phương thức set,get ta có thể thay đổi các giá trị thuộc tính và lấy giá trị từ chúng. Điều này làm cho chương trình dễ quản lý hơn và có thể kiểm soát dữ liệu tốt hơn.

// Lợi ích của việc sử dụng đối tượng  

Dễ dàng quản lý code khi có sự thay đổi chương trình.
Dễ mở rộng dự án.
Tiết kiệm được tài nguyên đáng kể cho hệ thống.
Có tính tái sử dụng cao.

// Khi nào ta sử dụng Abstract class

Nếu bạn muốn một lớp chứa một phương thức cụ thể nhưng bạn muốn triển khai thực sự phương thức đó để được quyết định bởi các lớp con, thì bạn có thể khai báo phương thức đó trong lớp cha ở dạng abstract.
Khi nào ta sử dụng Interface
Bạn muốn tạo một class Animals có các thuộc tính name, color. Sau bạn tạo thêm 2 class Fish và Cat, bởi vì 2 lớp này nó cũng có thuộc tính giống lớp Animals. Vì thế nó chỉ cần kế thừa từ lớp Animals, thì lớp Animals sẽ là abstract. Tuy nhiên, trong Animals có con biết bơi, có con sẽ không biết bơi, thế nên đây là thuộc tính không thể chung, cũng không nên để riêng, vì cũng nhiều con biết bơi mà. Thế nên bạn sẽ tạo ra 1 interface ISwim chẳng hạn, bây giờ bạn muốn con nào biết bơi thì cho nó implements là được.

// Override là gì (đưa ra ví dụ)
Override cho phép một lớp con cung cấp một triển khai cụ thể của phương thức đã được cung cấp bởi một trong các lớp cha của nó, có ví dụ ở tính trừu tượng.

// Overload là gì (đưa ra ví dụ)
Nguồn tham khảo: https://freetuts.net/overriding-va-overloading-trong-java-1141.html
Được định nghĩa là nạp chồng phương thức, có nghĩa là nếu trong một lớp có nhiều phương thức cùng tên nhưng khác nhau về số đối số truyền vào và các đối số có cùng kiểu dữ liệu, có cùng số đối số truyền vào và các đối số không có cùng kiểu dữ liệu, khác nhau trình tự kiểu dữ liệu của các đối số.

// Các access modifier trong java, khi dùng nó thì quyền truy cập sẽ như thế nào?
Nguồn tham khảo: https://huongdanjava.com/vi/access-modifier-trong-java.html
public: tất cả các class khác trong hay ngoài package và nội bộ class đều có thể truy cập đến các biến, các phương thức public của class này.
protected: chỉ những class ở cùng package hoặc những class extends từ class này và nội bộ class mới có thể truy cập đến các biến, phương thức public của class này.
default: chỉ những class ở cùng package với class này và nội bộ class thì mới có thể truy cập đến các biến, các phương thức public của class này.
private: chỉ những class nằm bên trong class này mới có quyền truy cập đến các biến, phương thức public của class này.


