TEST CODE(CLASS UserTest)

package com.codingproject;

import java.util.ArrayList;
import java.util.Scanner;

public class UserTest {
    private static Object ID;


    public static void main(String[] args) {
        int ID_NO, no_of_days;

        ArrayList<Admin> list = new ArrayList<>();
        list.add(new Admin ("Jane Shiro\t\t",301,3,2,200));
        list.add(new Admin ("Emmanuel Achinga",302,2,3,240));
        list.add(new Admin ("Dominic Sakwa\t",303,3,20,200));
        list.add(new Admin ("Dominic OCharo  ",304,1,10,400));
        Scanner in = new Scanner(System.in);

        System.out.println("ENTER YOUR ID NO.");
        ID_NO=  in.nextInt();
        if (ID_NO == 300){
            System.out.println("Welcome Admin");
            ID_NO = 1;}
        else if (ID_NO==301){
            System.out.println("Welcome Jane Shiro");
            ID_NO = 2;
        }
        else if (ID_NO==302){
            System.out.println("Welcome Emmanuel Achinga");
            ID_NO=3;
        }
        else if (ID_NO== 303){
            System.out.println("Welcome Dominic Sakwa");
            ID_NO=4;
        }
        else if (ID_NO==304){
            System.out.println("Welcome Dominic Ocharo");
            ID_NO=5;
        }
        switch (ID_NO){
       case 1:
       System.out.println("NAME\t\t\t\t\tID NO.\tSPEED\tDAYS\tPRICE");
       System.out.println(list.get(0));
       System.out.println(list.get(1));
       System.out.println(list.get(2));
       System.out.println(list.get(3));
        break;

       case 2: case 3: case 4: case 5:

       System.out.println("Speeds available are 1,2 and 3 mbps");
       System.out.println("Enter the speed you wish to pay for:");
       int Speed = in.nextInt();
       System.out.println("Monthly price for 1 mbps is 1200\n Monthly price for 2 mbps is 2400\n Monthly price for 3 mbps is 3000");
       System.out.println("Enter money paid:");
       int Price = in.nextInt();

       if (Speed == 1){
                    no_of_days = (int)Math.floor(Price/40);

                    System.out.println("Wifi will be active for: " + no_of_days + " days");
                }
       else if (Speed ==2){
                    no_of_days = (int) Math.floor(Price/80);
                    System.out.println("Wifi will be active for: " + no_of_days + " days");
                }
        else if (Speed ==3){
                    no_of_days= (int) Math.floor(Price/100);
                    System.out.println("Wifi will be active for: " + no_of_days + " days"); }
        break;
       default:
       System.out.println("ID NO. does not exist");
        break;
        }

    }
}


MAIN CODE(CLASS Admin)
package com.codingproject;

public class Admin {
        int ID,days,price,speed;
        String name;

        public Admin(String name,int ID,int speed,int days,int price) {
            this.ID = ID;
            this.name=name;
            this.speed=speed;
            this.days=days;
            this.price=price;
        }

    public String toString(){

        return  String.format("%s\t\t%d\t\t%d\t\t%d\t\t%d\t",name,ID,speed,days,price);
    }
}
