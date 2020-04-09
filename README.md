# Dice

Question 1: 

public class SimpleDiceNotation{ 

private int x = 0; //number 

private int n = 0; //sides 

 
public SimpleDiceNotation(){ 

    this.x = 1; 

    this.n = 6; 

}//default constructor 
 

public SimpleDiceNotation(String direction){ 

   int slashD = direction.indexOf("D"); 

   String number = direction.substring(0,slashD); 

   String side = direction.substring(slashD+1); 

   this.x = Integer.parseInt(number); 

   this.n = Integer.parseInt(side); 

}//String constructor 

 

public SimpleDiceNotation(SimpleDiceNotation copy){ 

    this.x = copy.x; 

    this.n = copy.n; 

}//copy constructor 

 

public int roll(){ 

  int sum = 0; 

  for(int i = 0; i<x;i++){ 

      sum += (int) (Math.random()*n+1); 

    } 

    return sum; 

} 

 

public String toString(){ 

    return x + "D" + n; 

} 

 

public boolean equals(){ 

    if(x == n)return true; 

    return false; 

} 

} 

 

 

Question 2: 

Part A: 

/** The parse method reads the String parameter myDice and fills the 

* sdnList with valid SimpleDiceNotation objects accordingly. Also 

* assigns a value to mod if necessary (leaves it as zero otherwise). 

* Precondition: myDice is a String that represents a valid Advanced Dice Notation 

Statement 

*/ 

private void parse(String myDice) { 

int i = 0; 

while (i >= 0){ 

sdnList = sdnList.add(i, myDice); 

i++; 

  } 

if(mod != 0){ 

sdnList = sdnList.add(mod); 

 } 

 

} 

 

Part B: 

/** The roll method rolls all the dice in the sdnList and returns the sum of these 

* rolls plus the modifier. 

*/ 

public int roll() { 

 int sum = 0; 

 for(int i = 0; i<sdnList.size();i++){ 

        for(int y = 0; y<x; y++){ 

      sum += (int) (Math.random()*n+1); 

    } 

 }  

if( mod != 0) sum += mod; 

return sum; 

} 

 

 
