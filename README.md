# Java_Casino_App
## This is a Desktop application for game of chance  this is Casino application

It run over desktop in cmd (command line)

It started by welcoming the player and ask him/her if their ready to play so you can press any button on your computer

![image](https://user-images.githubusercontent.com/103323625/192799591-bc6b2f05-796f-40b4-9fd8-e8d642a83053.png)

So after starting you you get two card with specified total and we give you a possiblility of hint(increasing total) or stay
if you  press 'hint' your total increase randomly so you have to make sure your total must be under 21 otherwise you loose the game
if you finally enter  'stay' so you can see the computer total 
so after that ,you get a result , if your total is greater than the Dealer's total you win else you loose


![image](https://user-images.githubusercontent.com/103323625/192801256-227be9de-2fb4-49d0-9054-010e9d88c622.png)

So after typing stay it is a Dealer (computer) turn for play as we see  the dealer loose the game beacause 
it hint and pass the limit of 21
 
 ![image](https://user-images.githubusercontent.com/103323625/192802328-efea80b6-a8f5-4c09-9e7d-6a6b994f496f.png)

this is a good application with working with function in java


```java

import java.util.Scanner;

public class BlackJack {

    public static  Scanner input = new Scanner(System.in);

    public static void main(String[] args) {
       
        System.out.println("\nWelcome to Java Casino!");
        System.out.println("Do you hava a knack for Black Jack?");
        System.out.println("\nWe shall see...");
        System.out.println("..Ready? Press anything to begin!");
        input.nextLine();

        int card1 = drawRandomCard();
        int card2 = drawRandomCard();

        System.out.println("\n You get a \n" + cardString(card1) + "\n and a \n"+ cardString(card2));
        int total = Math.min(card1,10) + Math.min(card2,10);
        System.out.println("Your total is: "+total);
        
        int dealerCard1 = drawRandomCard();
        int dealerCard2 = drawRandomCard();

        System.out.println("\n The dealer shows \n"+ cardString(dealerCard1)+ "\n and has a card facing down \n"+ faceDown());
        int dealerTotal = Math.min(dealerCard1,10) + Math.min(dealerCard2, 10);
        System.out.println("\nThe Dealer's Total is hidden");

        while(true){
             String option = hitOrStay();
             if(option.equals("stay")){
              break;
             }
             int newCard = drawRandomCard();
             total += Math.min(newCard, 10);
             System.out.println("\nYou get a\n"+cardString(newCard));
             System.out.println("Your total is "+ total);
              if(total > 21){
                     System.out.println("Bust!, Player loses.");
                     System.exit(0);
              }
        }


```
