# SE_OOP-assignment-2    [Identify commonalities and differences between Publication, Book and Magazine
                         classes. Title, Price, Copies are common instance variables and saleCopy is common
                         method. The differences are, Bookclass has author and orderCopies(). Magazine Class
                         has methods orderQty, Current issue, receiveissue().Write a program to find how
                         many copies of the given books are ordered and display total sale of publication]


import java.util.Scanner;
public class Main {
public static void main(String[] args) {
Book b = new Book();
Magazine m = new Magazine();
Publication p = new Publication();
Scanner sc = new Scanner(System.in);
while(true){
System.out.println("Enter");
System.out.println("1.Order Book");
System.out.println("2.Order Magazine");
System.out.println("3.Total Book Sell");
System.out.println("4.Total Magazine Sell");
System.out.println("5.Total Publication Sell");
System.out.println("6.Exit\n");
System.out.print("Enter Your Choice : ");
int choice = sc.nextInt();
System.out.print("\n");
switch (choice){
case 1:
b.getBookData();
b.saleCopy();
break;
case 2:
m.getData();
m.saleCopy();
break;
case 3:
b.totalBookSell();
break;
case 4:
m.totalMagSell();
break;
case 5:
p.saleCopy();
break;
case 6:
System.out.println("Exiting The Program..");
System.exit(0);
default:
System.out.println("Please Enter Valid Input..");
}
}
}
public class Book extends Publication{
String author;
public double bookSell;
public static double totalBookSell;
public Scanner sc = new Scanner(System.in);
void getAuthor(){
System.out.print("Enter Author's Name : ");
author = sc.nextLine();
}
void getBookData(){
getData();
getAuthor();
}
void orderCopies(){
System.out.print("Order Copies : ");
int newCopies = sc.nextInt();
this.copies = newCopies + this.copies;
}
@Override
void saleCopy(){
bookSell = (this.copies * this.price);
Book.totalBookSell += bookSell;
Publication.totalPrice += totalBookSell;
System.out.print("\n");
System.out.println("Ordered Book : " + this.title);
System.out.println("Total Amount : " + bookSell);
System.out.print("\n");
}
void totalBookSell(){
System.out.println("Total Book Sell : " + totalBookSell);
}
}
public class Publication {
String title;
double price;
int copies;
static double totalPrice;
Scanner sc = new Scanner(System.in);
void getData(){
System.out.print("Enter Title : ");
title = sc.nextLine();
System.out.print("Enter Price : ");
price = sc.nextDouble();
System.out.print("Enter Number of Copies : ");
copies = sc.nextInt();
}
void saleCopy(){
System.out.println("\nTotal Sell : " + (totalPrice));
}
void totalPublicationSell(){
System.out.println("Total Publication Sell : " + totalPrice);
}
}
public class Magazine extends Publication{
int orderQty;
String currentIssue;
public double MagSell;
public static double totalMagSell;
Scanner sc = new Scanner(System.in);
@Override
void saleCopy(){
MagSell = (this.copies * this.price);
Magazine.totalMagSell += MagSell;
Publication.totalPrice += totalMagSell;
System.out.print("\n");
System.out.println("Ordered Magazine :" + this.title);
System.out.println("Total Amount : " + MagSell);
System.out.print("\n");
}
void totalMagSell(){
System.out.println("Total Magazine Sell : " + totalMagSell);
}
}
