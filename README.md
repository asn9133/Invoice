package com.company;

import java.util.ArrayList;
import java.util.Scanner;

public class Main {

    public static void main(String[] args) {

        ArrayList<String> products = new ArrayList<String>();
        ArrayList<Double> prices = new ArrayList<Double>();

        products.add("Bison Sweater");
        prices.add(55.99);
        products.add("Bison Tee");
        prices.add(14.99);
        products.add("Bison Hoodie");
        prices.add(23.99);
        products.add("Bison Bumpersticker");
        prices.add(4.99);

        ArrayList<String> cart = new ArrayList<String>();
        ArrayList<Double> cart_price = new ArrayList<Double>();
        String answer = "";

        do {
            Scanner input = new Scanner(System.in);
            System.out.println("What do you want to do?");
            System.out.println("1) add purchase 2) finish purchase");
            answer = input.nextLine();

            if (answer.equals("1"))
            {
                for(int i=0; i<products.size(); i++)
                {
                    System.out.println(products.get(i) + " @ $" + prices.get(i));
                }

                System.out.print("What do you want to purchase?");
                String product;
                product =input.nextLine();
                int temp= -1;
                String product_purchase;
                Double product_price;

                for(int j=0; j< products.size(); j++)
                {
                    if(products.get(j).equals(product))
                    {
                        temp=j;
                    }
                }
                if(temp != -1)
                {
                    product_purchase= products.get(temp);
                    product_price = prices.get(temp);
                    cart.add(product_purchase);
                    cart_price.add(product_price);
                }
            }
        } while (! answer.equals("2"));

        double sum=0;
        double temp1;
        for(int k=0; k<cart_price.size(); k++)
        {
            temp1 = cart_price.get(k);
            sum = sum + temp1;
        }
        System.out.println("Your total is: $"+sum);
    }
}


