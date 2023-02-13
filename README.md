# OIBSIP
import java.util.*;
class Guessgame
{
	public void prepared()
	{
		Random rm=new Random();
		Scanner sobj=new Scanner(System.in);
		int value=rm.nextInt(101);
		System.out.println("A Random Number is generated");
		System.out.println("Enter the number of guesses you want to try.Guesses must be < 9");
		int ch=sobj.nextInt();
		while(ch>9)
		{
			System.out.println("Your chances exceeds. **Please Enter number < 9 **");
			ch=sobj.nextInt();
		}
		System.out.println("You have"+ch+"Chances");
		int fscore=100,dq=0;
		for(dq=0;dq<ch;dq++)
		{
			
			System.out.println("Enter the number you guessed.Chance no"+(dq+1));
			int number=sobj.nextInt();
			if(number==value)
			{
				System.out.println("That's Amazing ...You won the Game");
				System.out.println("Your score is "+fscore);
				break;
			}
			else if(number>value)
			{
				System.out.println("Your number is greater than the original number");
			}
			else
			{
				System.out.println("Your number is less than the original number");
			}
			fscore-=10;
		} 
		if(dq>=ch)
		{
		    System.out.println("Alas!,You Lost the game");
			System.out.println("The number is "+value);
			System.out.println("Your score is: 0");
		}
	}
}
class Main
{
public static void main(String args[])
{
	System.out.println("Java developer Task-2");
	Scanner sobj=new Scanner(System.in);
	Guessgame f=new Guessgame();
	System.out.println("Shall we start the game ? : Yes/No");
	String str=sobj.nextLine();
	while(str.equalsIgnoreCase("Yes")||str.equalsIgnoreCase("y"))
	{
		f.prepared();
		System.out.println("Do you want to proceed ? Yes/No");
		str=sobj.nextLine();
	}
	System.out.println("Game closed!!!");
}
}
