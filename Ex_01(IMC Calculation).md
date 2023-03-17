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
    
    public Persona(){
        
    }        
    private float weigth,heigth;
    
    public void setWeigth(float weigth){
        this.weigth = weigth;
    }
    
    public float getWeigth(){
        return weigth;
    }
    public void setHeigth(float heigth){
        this.heigth = heigth;   
    }
    
    public float getHeigth(){
        return heigth;
    }
    
    
    
    
}
```
#### MethPersona Class
```
 package ExercisesJavaPoo;


public class MethPersona  {
       
    public float calculateIMC(Persona p){
        
        float IMC = p.getWeigth()/ (float)Math.pow(p.getHeigth(), 2);
        return IMC;
    }
    public String levelIMC(float IMC){
        String level= "";
        
        if(IMC<=18.5){
            
            level = "Thinness";
            
        }else if(IMC>18.5 && IMC<=24.9){
        
            level = "Normal";
              
         }else if(IMC>24.9 && IMC<=29.9){
        
            level = "Overweigth";
              
         }else if(IMC>29.9 && IMC<=39.9){
        
            level = "Obesity";
              
         }
        return level;
    }
    
}

```
