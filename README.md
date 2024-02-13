# Number-Guessing-Game-
import java.util.*;

class NumberGame_1{
    public int number;
    public int inputnumber;
    public int noofguessses=0;

    public int getnoofguessses(){
        return noofguessses;
    }
    public void setnoofguessses(int noofguessses){
        this.noofguessses=noofguessses;
    }

    NumberGame_1(){
        Random R =new Random();
        this.number=R.nextInt(100);
    }
    void takeinputfromuser(){
        Scanner sc = new Scanner(System.in);
        System.out.println("Guess the Number :");
        inputnumber=sc.nextInt();
    }

    boolean isCorrectnumber(){
        noofguessses++;
        if(inputnumber==number){
            System.out.format("YES,You have Guesssesd it Right , it was %d",number);
            System.out.format("\nYou Guesssesd it in %d attempts ",noofguessses);
            return true;
    }else if(inputnumber<number){
        System.out.println("Number is too LOW...");
    }else if(inputnumber>number){
        System.out.println("Number is too HIGH... ");
    }
        return false;
    
    }
    public static void main(String[] args) {
        NumberGame_1 N=new NumberGame_1();
        boolean b=false;
        while(!b){
            N.takeinputfromuser();
            b=N.isCorrectnumber();
        }
    }


}
