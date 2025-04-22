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
