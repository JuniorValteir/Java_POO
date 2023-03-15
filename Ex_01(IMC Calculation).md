# Java_POO
## Example 01 (IMC Calculation)

#### Main Class
``` 
package ExercisesJavaPoo;
import java.util.Scanner;  
public class App {
 

    public static void main(String[] args) {
        
        Scanner sc = new Scanner(System.in);
        
        Persona objectPersona = new Persona();
                
        System.out.println("Enter the weigth: ");
        objectPersona.weigth = sc.nextFloat();
        System.out.println("Enter the heigth: ");
        objectPersona.heigth = sc.nextFloat();
        
        System.out.println("Your IMC: "+String.format("%.2f",objectPersona.calculateIMC())+"\n");
        System.out.println("IMC Level: "+objectPersona.levelIMC());
 
    }
}

```
#### Persona Class
```
package ExercisesJavaPoo;

public class Persona {
    
    double weigth,heigth;
    
    public double calculateIMC(){
        
        double IMC = weigth/Math.pow(heigth, 2);
        return IMC;
    }
    public String levelIMC(){
        String level= "";
        if(calculateIMC()<=18.5){
            
            level = "Thinness";
            
        }else if(calculateIMC()>18.5 && calculateIMC()<=24.9){
        
            level = "Normal";
              
         }else if(calculateIMC()>24.9 && calculateIMC()<=29.9){
        
            level = "Overweigth";
              
         }else if(calculateIMC()>29.9 && calculateIMC()<=39.9){
        
            level = "Obesity";
              
         }
        return level;
    }
    
}
```
