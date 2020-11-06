# java-learning-by-mosh
created java scripts

mortgage calculator in java scripts M = p * r(1+r)^n/ r(1+r)^n-1

package com.company;


import java.text.NumberFormat;
import java.util.Scanner;

public class Main {

    public static void main(String[] args) {
        final double noOfMonths = 12;
        final double Percent = 100;

        Scanner input = new Scanner(System.in);
        System.out.print("Principal: ");
        double Principal = input.nextDouble();

        System.out.print("Annul Interest Rate: ");
        double Annul_Interest_Rate = input.nextDouble();
        double monthlyInterestRate = Annul_Interest_Rate / Percent / noOfMonths;

        System.out.print("Period (Years): ");
        double Period_inYears = input.nextDouble();
        double periodsInMonths = Period_inYears * noOfMonths;

        double one_plus_r_wholepower_n = Math.pow(( 1 + monthlyInterestRate), periodsInMonths);

        double Mortgage = Principal * monthlyInterestRate *one_plus_r_wholepower_n
                          / (one_plus_r_wholepower_n-1);

        String mortgageFormated = NumberFormat.getCurrencyInstance().format(Mortgage);
        System.out.print("Mortgage: " + mortgageFormated);

    }
}
