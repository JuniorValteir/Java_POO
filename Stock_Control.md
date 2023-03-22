# Java_Exercises
## Example Stock Control

#### Main Class
``` 
package application;
import java.util.Locale;
import java.util.Scanner;
import entities.Product;

public class App {
    public static void main(String[] args) {
        Locale.setDefault(Locale.US);
        Scanner sc = new Scanner(System.in);
        int answer;
        
        System.out.println("Enter product data: ");
        System.out.print("Name: ");
        String name = sc.nextLine();
        
        System.out.print("Price: ");
        double price = sc.nextDouble();
        
        System.out.print("Quantity in stock: ");
        int quantity = sc.nextInt();
        
        
        Product product = new Product(name, price, quantity);
        
        
        System.out.println();
        System.out.println("Product data: " + product);
        System.out.println();
        
        String keep = "s";
        while(keep.equals("s")){

            System.out.println
                    ("Choose an Option\n"+
                    "1- Add product in Stock\n"+
                    "2- Remove product in Stock\n");
            answer = sc.nextInt();
            
            if(answer == 1){
                System.out.print("Enter the number of products to be added in stock: \n");
                quantity = sc.nextInt();
                product.addProducts(quantity);
                System.out.println("Updated data: " + product+"\n");
                System.out.println();
                
            }else if(answer == 2){
                System.out.print("Enter the number of products to be removed from stock: ");
                quantity = sc.nextInt();
                product.removeProducts(quantity);
                System.out.println();
                System.out.println("Updated data: " + product);
            }else{
                System.out.println("!! Wrong choise !!");
                
            }
            System.out.println("Continue?");
            keep = sc.next();
            
        }
        
        sc.close();
    }
}

```
#### Product CLass
```
package entities;
public class Product {
    public String name;
    public double price;
    public int quantity;
    
    public Product(String name, double price, int quantity){
    
        this.name = name;
        this.price = price;
        this.quantity = quantity;
    
    }
    
    
    public double totalValueInStock() {
        return price * quantity;
    }
    public void addProducts(int quantity) {
        this.quantity += quantity;
    }
    public void removeProducts(int quantity) {
        this.quantity -= quantity;
    }
    public String toString() {
        return name
                + ", $ "
                + String.format("%.2f", price)
                + ", "
                + quantity
                + " units, Total: $ "
                + String.format("%.2f", totalValueInStock());
    }
}
```
