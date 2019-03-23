# MatchTickets

import java.util.Scanner;

public class P32_MatchTickets {
    public static void main(String[] args) {

        Scanner scanner = new Scanner(System.in);

        double budget = Double.parseDouble(scanner.nextLine());
        String ticketType = scanner.nextLine();
        int numberPersons = Integer.parseInt(scanner.nextLine());

        double transportPrice = 0;
        double remainingMoney = 0;

        if (numberPersons >= 1 && numberPersons <= 4) {
            transportPrice = budget * 0.75;

        }
        else if (numberPersons >= 5 && numberPersons <= 9) {
            transportPrice = budget * 0.60;

        }
        else if (numberPersons >= 10 && numberPersons <= 24) {
            transportPrice = budget * 0.50;

        }
        else if (numberPersons >= 25 && numberPersons <= 49) {
            transportPrice = budget * 0.40;

        }
        else if (numberPersons >=50){
            transportPrice = budget * 0.25;

        }


        if (ticketType.equalsIgnoreCase("normal")){
            remainingMoney = budget - (transportPrice + (numberPersons * 249.99));

        }
        else if (ticketType.equalsIgnoreCase("vip")){
            remainingMoney = budget - (transportPrice + (numberPersons * 499.99));

        }

        if (remainingMoney > 0){
            System.out.printf("Yes! you have %.2f leva left.", remainingMoney);

        }
        else if (remainingMoney < 0){
            System.out.printf("Not enough money! You need %.2f leva.", Math.abs(remainingMoney));

        }





    }

}
