# Banking-Management
package Com.java.pjt;
import java.util.*;
public class Account {

	public static void main(String[] args) {
		BankAccount obj = new BankAccount("Gagan Baghel" , "*JDK-910*");
		obj.ShowMenu();
	}

}

class BankAccount{
	int balance;
	int previousTransaction;
	String customerName;
	String customerId;
	
    BankAccount(String cname , String cid){
	customerName = cname;
	customerId = cid;
	}
	
	void Deposit(int amount)
{
		if(amount != 0) {
			balance = balance + amount;
			previousTransaction = amount;
		}
}

void withdraw(int amount) {
	if(amount != 0) {
		balance = balance - amount;
		previousTransaction = - amount;
		
	}
 }
       void getPreviousTransaction() {
    	   if(previousTransaction > 0) {
    		   System.out.println("Deposited: " + previousTransaction);
    	   }
    	   else if(previousTransaction < 0) {
    		   System.out.println("Withdraw:" +Math.abs(previousTransaction));
    	   }
    	   else {
    		   System.out.println(" No Transaction Occured");
    		   
    	   }
       }
       
        void ShowMenu() {
        	
          char option = '\0';
          Scanner sc=new Scanner(System.in);
          
          System.out.println("Welcome " +customerName);
          System.out.println("My ID " +customerId);
          System.out.println();
          
          System.out.println("A : Check Your Balance");
          System.out.println("B :Deposit");
          System.out.println("C :Withdraw");
          System.out.println("D :Previous Transaction");
          System.out.println("E :Exit The System");
          
          do {
        	 System.out.println("****************************************************************");
        	 
            System.out.println("Enter Your Option");
            System.out.println("****************************************************************");
            option = sc.next().charAt(0);
            System.out.println();

             switch(option) {
             case 'A':
            	 System.out.println("***************************************************");
            	 System.out.println("Balance =" +balance);
            	 System.out.println("*******************************************");
            	 System.out.println();
             	
            	 break;
            	 
             case 'B':
            	 System.out.println("***************************************************");
            	 System.out.println("Enter Amount to deposit");
            	 System.out.println("*******************************************");
            	 
            	 int amount = sc.nextInt();
            	 Deposit(amount);
         
            	 System.out.println();
            	
            	 break;
            	 
             case 'C':
            	 System.out.println("***************************************************");
            	 System.out.println("Enter Amount to Withdraw");
            	 System.out.println("*******************************************");
            	 
            	 int amount2 = sc.nextInt();
            	 withdraw(amount2);
            	
            	 System.out.println();
            	 break;
            	 
             case 'D':
            	 System.out.println("***************************************************");
            	 getPreviousTransaction();
            	 System.out.println("***************************************************");
            	 System.out.println();
            	 break;
            	 
             case 'E':
            	 System.out.println("****************************************************");
            	 break;
                default:
                	System.out.println("Invalid Option !! Please Enter Correct Option..");
                	break;
             }
          }
          while(option != 'E');
        		  System.out.println("Thank you for Using our Services....");
          }
            
      }     
