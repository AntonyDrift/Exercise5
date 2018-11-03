package com.company;

import java.util.Scanner;

public class Main {

    public static void main(String[] args) {
        Scanner scan = new Scanner(System.in);
        Bank xMenu = new Bank(50, 20, 10);
        xMenu.mainMenu();
    }
}

class Bank {
    int n20;
    int n50;
    int n100;
    int sum;
    int key;
    Scanner scan = new Scanner(System.in);
    int mod100;
    int mod50;
    int mod20;
    int modX100;
    int modX50;
    int modX20;
    int comp100 =0;
    int comp50=0;
    int comp20=0;
    int res100=0;
    int res50=0;
    int res20=0;
    
    public Bank(int n20, int n50, int n100) {
        this.n20 = n20;
        this.n50 = n50;
        this.n100 = n100;
        this.sum = n20 * 20 + n50 * 50 + n100 * 100;
    }

    public int getN20() {
        return n20;
    }

    public void setN20(int n20) {
        this.n20 = n20;
    }

    public int getN50() {
        return n50;
    }

    public void setN50(int n50) {
        this.n50 = n50;
    }

    public int getN100() {
        return n100;
    }

    public void setN100(int n100) {
        this.n100 = n100;
    }

    public void mainMenu() {
        System.out.println("********ATM********\n1. Deposit money\n2. Withdraw money\n3. Check balance\nPress \"0\" to disconnect");
        key = scan.nextInt();
        switch (key) {
            case 1:
                depositMoney();
                break;
            case 2:
                withdrawMoney();
                break;
            case 3:
                checkBalance();
                break;
            case 4:
                checkMoney();
        }
    }
    
    public void depositMoney() {
        System.out.println("********ATM********\nChoose banknotes:\n1.20 dollars\n2.50 dollars\n3.100 dollars\nPress \"0\" to return");
        key = scan.nextInt();
        switch (key) {
            case 1: {
                System.out.println("How much?");
                key = scan.nextInt();
                n20 += key;
                sum += key * 20;
                depositMoney();
                break;
            }
            case 2: {
                System.out.println("How much?");
                key = scan.nextInt();
                n50 += key;
                sum += key * 50;
                depositMoney();
                break;
            }
            case 3: {
                System.out.println("How much?");
                key = scan.nextInt();
                n100 += key;
                sum += key * 100;
                depositMoney();
                break;
            }
            case 0: {
                mainMenu();
            }
        }
    }

    public boolean checkMoney() {
      return ((key<=sum)
              &&
              ((key % 100 % 50 % 20 == 0)|| (key % 100 % 20 == 0)|| (key % 50 % 20 == 0)|| (key % 50 == 0)|| (key % 20 == 0)));
    }

    public void withdrawMoney() {
        System.out.println("vvod");
        key=scan.nextInt();
        checkMoney();
        
        if (checkMoney()==true) {
            System.out.println("good");
            
            if (key % 100 == 0) {
                comp100 = key / 100; checkN100();
                
            } else {comp100 = key / 100; modX100 = key % 100;
            
                if (modX100 % 20 == 0) {checkN20();
                } else if (modX100 % 50 == 0) {
                    checkN50();
                    
                } else {
                    comp50 = modX100 / 50;
                    modX50 = modX100 % 50;
                    comp20 = modX50 / 20;
                }
            }
            System.out.println("n20 "+res20+" n50 "+res50+" n100 "+ res100);
            sum-=res20*20+res50*50+ res100 *100;
            this.n20-=res20;
            this.n50-=res50;
            this.n100-= res100;
            mainMenu();
        } else {
            System.out.println("bad"); checkMoney();
        }
    }

    public void checkN100() {
        if (comp100 <= n100) {
            res100 = key / 100;
        } else {
            mod100 = Math.abs(comp100 - n100);
            res100 = comp100 - mod100;
            comp50 = (mod100 * 2);

            if (comp50 <= n50) {
                res50 = comp50;
            } else {
                mod50 = Math.abs(comp50 - n50);
                res50 = comp50 - mod50;

                if (comp20 <= n20) {
                    res20 = (mod50 * 5 / 2);
                } else {
                    System.out.println("wrong");
                }
            }
        }
    }
    
    public void checkN50(){
        if (comp100 <= n100) {
            res100 = key / 100;
        } else {
            mod100 = Math.abs(comp100 - n100);
            res100 = comp100 - mod100;
            comp50 = (mod100 * 2);

            if (comp50 <= n50) {
                res50 = comp50;
            } else {
                mod50 = Math.abs(comp50 - n50);
                res50 = comp50 - mod50;

            if (comp20 <= n20) {
                    res20 = (mod50 * 5 / 2);
                } else {
                    System.out.println("wrong");
                }
            }
            res50-=1; res20+=5;
            }
    }

    public void checkN20() {
        if (comp100 <= n100) {
            res100 = key / 100;
        } else {
            mod100 = Math.abs(comp100 - n100);
            res100 = comp100 - mod100;
            comp50 = (mod100 * 2);
            
            if (comp50 <= n50) {
                res50 = comp50;
            } else {
                mod50 = Math.abs(comp50 - n50);
                res50 = comp50 - mod50;
                
                if (comp20 <= n20) {
                    res20 = (mod50 * 5 / 2);
                } else {
                    System.out.println("wrong");
                }
            }
            res50 -= 1;
            res20 += 5;
        }
    }
    
    public void checkBalance() {
        System.out.println("********ATM********\nYour balance is " + sum + " dollars\nAmount of banknotes:" + "\n20 dollars: " + getN20() + "\n50 dollars: " + getN50() + "\n100 dollars: " + getN100() + "\nPress \"0\" to return");
        key = scan.nextInt();
        if (key == 0) {
            mainMenu();
        }
    }
}
