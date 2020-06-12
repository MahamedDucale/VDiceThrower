package com.elec0021;

import java.util.*;

public class VDiceThrower {
    private int no_of_sides;//declare instance variables
    private int no_of_throws;
    public void set_no_of_sides(Scanner input) throws Exception{
        System.out.println("Enter the number of sides:\n");
        try{
        int i = input.nextInt();
            if(i<2){ //if number of arguments less than 2, throw InputMismatchException
                throw new InputMismatchException();
            }else{
                this.no_of_sides = i;// set number_of_sides to input
            }
        }catch(Exception e){
            input.nextLine();//exception caught so progress the scanner
            throw new Exception("Invalid number of sides,try again.\n");//rethrow exception for handling by main function
        }

    }
    public void set_no_of_throws(Scanner input) throws Exception{
        System.out.println("Enter the number of throws:\n");
        try{
        int i = input.nextInt();
        if((i > 0) && (i%this.no_of_sides != 0)){ //if number of throws positive and multiple of no_of_sides no exception raised
            throw new InputMismatchException();
        }else{
            this.no_of_throws = i; //set no_of_throws to value of input
        }
        }catch (Exception e){
            input.nextLine();//exception caught so advance the scanner
            throw new Exception("Invalid number of throws,try again.\n");//rethrow exception for handling by main function
        }
    }
    public int get_no_of_sides(){//public getter method for no_of_sides
        return this.no_of_sides;
    }
    public int get_no_of_throws(){//public getter method for no_of_throws
        return this.no_of_throws;
    }
    public VDiceThrower(){//VDiceThrower constructor
        this.no_of_sides = 0; //instance variables initialised
        this.no_of_throws = 0;
    }
    public static void main(String[] args) {
        int ex = 1;//define variables
        int current_side;
        VDiceThrower VDiceThrower_obj = new VDiceThrower();//instantiate VDiceThrower object
        Random randGen = new Random(); // create new random generator object
        Scanner user_input = new Scanner(System.in);//instantiate Scanner object
        while(ex == 1){//loop continues until correct input received
        try {
            VDiceThrower_obj.set_no_of_sides(user_input);
            VDiceThrower_obj.set_no_of_throws(user_input);
            ex = 0;//try successful, therefore set ex to 0 to exit while loop
        }catch (Exception e){
            System.out.println(e.getMessage());//print error message of exception
        }
        }
        int[] side_count = new int[VDiceThrower_obj.get_no_of_sides()];//array with each element = number of throws
        for(int i = 0;i< VDiceThrower_obj.get_no_of_throws();i++){//for loop to simulate dice throws
             current_side = randGen.nextInt(VDiceThrower_obj.get_no_of_sides()) + 1;//side that is rolled stored in current_side
             side_count[current_side - 1] = side_count[current_side - 1] + 1;//element representing side that is rolled incremented
        }
        for(int i = 0;i<side_count.length;i++){//for loop prints number of throws for each side
            System.out.printf("%d throws of %d \n",side_count[i],i+1);
        }


    }
}
