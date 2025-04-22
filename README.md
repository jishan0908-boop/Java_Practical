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
