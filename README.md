
import java.io.*;
import java.util.*;
public class Main
{
	public static void main(String[] args) {
		Scanner sc=new Scanner(System.in);
	
		
		String NewsPapers[]={"TOI","Hindu","ET","BM","HT"};
		float NewsPaperPrice[][]=new float[5][7];
		float NewsPaperWeeklySum[]=new float[5];
		
		System.out.println("Please Enter the test case");
		
		//taking user input
		for(int i=0;i<NewsPapers.length;i++){
		    for(int j=0;j<7;j++){
		        NewsPaperPrice[i][j]=sc.nextFloat();
		    }
		}
		
		System.out.println();
		System.out.println("The Enterd values are");
		
		//printing for verifying
		for(int i=0;i<NewsPapers.length;i++){
		    for(int j=0;j<7;j++){
		        System.out.print(NewsPaperPrice[i][j]+" ");
		    }
		    System.out.println();
		}
		
		
		float sum=0.0f;
	
		//adding all the day price of NewsPapers
		for(int i=0;i<NewsPapers.length;i++){
			    sum=0;
		    for(int j=0;j<7;j++){
		        sum=sum+NewsPaperPrice[i][j];
		    }
		    NewsPaperWeeklySum[i]=sum;
		}
		
		System.out.println();
		System.out.println("these are the weekly price of NewsPapers");
		
		//printing the weekly prices of NewsPapers
		for(int i=0;i<NewsPaperWeeklySum.length;i++){
		    System.out.println(NewsPaperWeeklySum[i]);
		}
		
		//user price limit input
		System.out.println("Enter the price limit");
		
		int PriceLimit=sc.nextInt();
		
		System.out.println();
		System.out.println("These are the NewsPapers can be afford");
		//calculating and printing the appropriate NewsPapers
		for(int i=0;i<NewsPaperWeeklySum.length;i++){
		    for(int j=i+1;j<NewsPaperWeeklySum.length;j++){
		        sum=NewsPaperWeeklySum[i]+NewsPaperWeeklySum[j];
		        
		        if(sum<=PriceLimit){
		            System.out.print("('"+NewsPapers[i]+"',"+"'"+NewsPapers[j]+"') ");
		        }
		    }
		}
		
	}
	

}


test case
3 3 3 3 3 5 6
2.5 2.5 2.5 2.5 2.5 4 4
4 4 4 4 4 4 10
1.5 1.5 1.5 1.5 1.5 1.5 1.5
2 2 2 2 2 4 4

Input    Output
40      {“TOI”, “BM”}, {“BM”, “HT”}, {“Hindu”, “BM”}, {“Hindu”, “HT”}
35      {“BM”, “HT”}, {“Hindu”, “BM”}
