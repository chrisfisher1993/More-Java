import java.io.*;

public class Skateboard 
{ 
  //Instance Variables
  private int area;
  private Double width;
  private String color;
  
   //Default Constructor
  public Skateboard()
  {
   this(0,0.0,"null");  
  }
  
  //Parameterized Constructor
  public Skateboard(int area, Double width, String color)
  {
    this.area = area;
    this.width = width;
    this.color = color;
  }
  
  //getters and setters
 
/*
* This method will get the area of instance variable
*
* @params void
*
* @return int
*/ 
  public int getArea()
 {
   return area;
 }
  
/*
* This method will set the area of instance variable
*
* @params int
*
* @return void
*/
 public void setArea (int area)
 {
   this.area =area;
 }
  
/*
* This method will get the width of instance variable
*
* @params void
*
* @return double
*/
 public double getWidth()
 {
   return width;
 }
 
/*
* This method will set the width of instance variable
*
* @params double
*
* @return void
*/
 public void setWidth (double width)
 {
   this.width =width; 
 }
 
 /*
* This method will get the color of instance variable
*
* @params void
*
* @return String
*/ 
 public String getColor()
 {
   return color;
 }
 
 /*
* This method will set the color of instance variable
*
* @params String
*
* @return void
*/
 public void setColor (String color)
 { 
   this.color =color;
 }
        
/*
* This method will display the values of instance variables
*
* @params void
*
* @return void
*/
   void display()
  {
    System.out.print(area+", ");
    System.out.print(width+", "); 
    System.out.print(color+"\r"+"\n");
    }
  
/*
* This method will loop the array created in the Demos class
* 
* @params array
* 
* @return void
*/ 
  public static void displayAllObjects(Skateboard[] skateArr)
  {
  for(int index =0; index < skateArr.length; index++)
        skateArr[index].display();
  }

/*
* This method contains a string builder object and loops the array created 
* in the demo class
* 
* @params array
* 
* @return void
*/
  public static void createSpreadsheet(Skateboard[] skateArr) throws IOException
  {  
    StringBuilder str = new StringBuilder("Area, Width, Color \n");
    for(int index = 0; index < skateArr.length; index++) 
      str.append(skateArr[index].area + skateArr[index].width + skateArr[index].color);
    
  //Specifies file output is written upon                 
  FileWriter fw = new FileWriter("mydata.csv", true);
  PrintWriter pw = new PrintWriter(fw);
  
  //Print string builder object onto specified file
  pw.print(str);   
  }  
}


