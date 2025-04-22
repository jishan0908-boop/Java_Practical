# Java_Practical

## 1. Design a class Complex having a real part (x) and an imaginary part (y). Provide methods to perform the following on complex numbers: a. Add and Multiply two complex numbers. b. toString() method to display complex numbers in the form: x + i y 

```
import java.util.Scanner;
import java.io.*;
class Complex{
	public double real;
	public double imaginary;
	
	public Complex(double real ,double imaginary){
	this.real = real;
	this.imaginary = imaginary;
	}
	
	public static void toString(Complex c){
		System.out.println(c.real + "+i" + c.imaginary);
	}
	
	public static void add(Complex c1 , Complex c2 , Complex c3){
		double value_x = c1.real + c2.real;
		double value_y = c1.imaginary + c2.imaginary;
		c3.real = value_x;
		c3.imaginary = value_y;
		System.out.println("Adding C1 and C2");
		System.out.print("C1 = ");
		toString(c1);
		System.out.print("C2 = ");
		toString(c2);
		System.out.print("Final Answer = ");
		toString(c3);
	}
	
	public static void multiple(Complex c1, Complex c2){
		double ans = (c1.real*c2.real) - (c1.imaginary*c2.imaginary);
		System.out.println("Multiplying C1 and C2");
		System.out.print("C1 = ");
		toString(c1);
		System.out.print("C2 = ");
		toString(c2);
		System.out.println("Answer is = "+ans);
		
	}
}
	
class practical_1{
	public static void main(String args[]){
		Complex c1 = new Complex(12.12,23.23);
		Complex c2 = new Complex(23,56);
		Complex c3 = new Complex(0,0);
		Complex.add(c1,c2,c3);
		Complex.multiple(c1,c2);
	}
	}
```



## Create a class TwoDim which contains private members as x and y coordinates in package P1. Define the default constructor, a parameterized constructor and override toString() method to display the co- ordinates. Now reuse this class and in package P2 create another class ThreeDim, adding a new dimension as z as its private member.
```
package P1;
import java.util.Scanner;
import java.io;
class TwoDim{
	private int x;
	private int y;
	
	public TwoDim(){
		this.x = 0;
		this.y = 0;
	}
	
	public TwoDim(int x,int y){
		this.x = x;
		this.y = y;
	}
	
	@Override
	public String toString(){
		return "Coordinates x : " + x +" y : " + y ;
	}
}
```
```
package P2;

import P1.TwoDim;

class ThreeDim extends TwoDim{
	private int z;
	
	public ThreeDim(){
		super();
		this.z = 0;
	}
	
	public ThreeDim(int x ,int y,int z){
		super(x,y);
		this.z =z;
	}
	
	@Override
	public String toString(){
		return super.toString() + " z : " + z;
	}
}
```
```
package P;
import P1.TwoDim;
import P2.ThreeDim;
class practical_2{
	public static void main(String args []){
         TwoDim point1 = new TwoDim(5, 10);
        ThreeDim point2 = new ThreeDim(5, 10, 15);
        System.out.println("Using TwoDim object:");
        displayCoordinates(point1);  
        System.out.println("\nUsing ThreeDim object:");
        displayCoordinates(point2);  
    }


    public static void displayCoordinates(TwoDim point) {
        System.out.println(point.toString());
    }
}
```

## Define an abstract class Shape in package P1. Inherit two more classes: Rectangle in package P2 and Circle in package P3. Write a program to ask the user for the type of shape and then using the concept of dynamic method dispatch, display the area of the appropriate subclass. Also write appropriate methods to read the data. The main() function should not be in any package.


```
package P2;

class Rectangle{
	public int length;
	public int breadth;
	
	public Rectangle(){
		this.length = 0;
		this.length = 0;
	}
	
	public Rectangle(int length , int breadth){
		this.length = length;
		this.breadth = breadth;
	}
	
	public static displayaArea(){
		return "Area of Rectangle : " + length*breadth ;
	}
}
```

```
package P3;

class Cricle{
	public int radius;
	
	public Cricle(){
		this.radius = 0 ;
	}
	
	public Cricle(int radius){
		this.radius = radius;
	}
	
	public static displayArea(){
		float area = 3.14 * radius * radius;
		return "Area of Circle : " + area;
	}
}
```
```
package P1;

import P2.Rectangle;
import P3.Circle;

class Shape{
	private Rectangle rec;
	private Circle cr;
	
	public Shape(int check , int length , int breadth){
		if (check == 1){
			rec = new Rectangle(length,breadth);
			
		}
		 else {
            System.out.println("Invalid check value for this constructor.");
        }
	
	public Shape(int check , int radius){
		if (check == 2){
			cr = new Circle(radius);
			
		}
		 else {
            System.out.println("Invalid check value for this constructor.");
        }
        
        public void display(){
        	if (rec != null){
        		System.out.println(rec.displayArea());
        	}
        	if (cr != null){
        		System.out.println(cr.displayArea());
        	}
}
```
```
import java.util.Scanner;
import P1.Shape;
class practical_3{
	public static void main(String args[]){
	Scanner sc = new Scanner(System.in);
	System.out.print("Enter 1 for Rectangle else enter 2 for Circle");
	int check = sc.nextInt();
	if (check == 1 ){
		System.out.print("Enter length : ");
		int len = sc.nextInt();
		System.out.println();
		System.out.print("Enter breadth : ");
		int br = sc.nextInt();
		System.out.println();
		Shape sh = new Shape(check , len ,br);
		sh.display();
	}
	if (check == 2){
		System.out.print("Enter the radius : ");
		int r = sc.nextInt();
		System.out.println();
		Shape sh1 = new Shape(check , r);
		sh1.display();
	}
	else{
		System.out.println("Invalid Choice");
	}
}
```

## Create an exception subclass UnderAge, which prints “Under Age” along with the age value when an object of UnderAge class is printed in the catch statement. Write a class exceptionDemo in which the method test() throws UnderAge exception if the variable age passed to it as argument is less than 18. Write main() method also to show working of the program.

```
import java.util*;

public class UnderAge{
	public static void InvaildAgeExeception(String message){
		super(message);
	}
}

public class Checker{
	public static void validAge(int age) throws InvaildAgeExeception[
		if(age < 18) {
		throw new InvalidAgeExecption("The persons is under age and his age is : " + age);
	}
}

public class java_4{
	public static void main(String args[]){
		try{
			int age = 17;
			validAge(age);
			System.out.print("You are eligible for vote.");
		}
		catch(InvalidAgeExeception e){
			System.out.println("Caught an Exeception : " + e.getMessage());
		}
	}
}
```
		
		
