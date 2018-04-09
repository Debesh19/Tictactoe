# Tictactoe
import java.util.Scanner;
public class SahuTTT{
 public static void main(String[] args){

 Scanner reader = new Scanner(System.in);
   TicTacToeBoard board = new TicTacToeBoard(620,720);

// This in array is drawing up the board lines. In (xstart, ystart, xend, yend) format
  int[][]boardLine = {{0,200,600,200},
    	{0,400,600,400},
    	{200,0,200,600},
    	{400,0,400,600}};

// This sets up the array that will be used to set up the X/O grid. They are temporarily filled with hyphens until they are fiflled with x and o values.
  char [][]arr = new char[3][3];

 for (int i=0;i<3;i++)
   for (int j=0;j<3;j++)
    arr[i][j]='-';



 // This line imports the TicTacToeBoard file
 // This sets up the grid given the lines you provided above in the boardLine array
   board.defineBoard(boardLine);
 // This will set your pictures to display for the x and o values. Make sure your names match exactly what you type in the parameters.
   board.setFiles("X.png","O.png");
 // This sets up the spacing and place values for x and o
   board.setBoard(arr);
 // This will refresh the board so that new elements will display.
   board.repaint();



				System.out.println("\t\t\tTIC-TAC-TOE\n\n(Rows input 0-2, Coloumn input 0-2)");


				System.out.println("\nWould you like to play one player (1) or two player (2) ?");
  		  			int g1 = reader.nextInt();




if(g1==1){
//player1
		int turns = 0;
		boolean turn2 = true;
		boolean turn1 = true;







			for(int x = 0; x < 9; x++){
   					while(turn1 == true){
   					System.out.println("What row would you like to choose?");
  		  			int a1 = reader.nextInt();

				while(a1>2||a1<0){
				System.out.println("\n Enter a number 0-2");
				 a1 = reader.nextInt();
				}


				System.out.println("What coloumn would you like to choose?");
				int b1 = reader.nextInt();

					while(b1>2||b1<0){
					System.out.println("\n Enter a number 0-2");
					 b1 = reader.nextInt();
				}



					if(arr[a1][b1]=='-'){
					 arr[a1][b1]='x';
					 board.repaint();
					 turn1 = false;
					 turn2 = true;
					}

					else{
						System.out.println("Pick an open spot!\n\n");
					}


//ai
				   while(turn2==true){
					int ai1= (int) (Math.random()*3)+0;
					int ai2= (int) (Math.random()*3)+0;
					 if(arr[ai1][ai2]=='-'){
					 arr[ai1][ai2]='o';

					board.repaint();
					 turn2 = false;
					 turn1 = true;
					 }




//wins

  				if(((arr[0][0] == 'o') && (arr[0][1] == 'o') && (arr[0][2] == 'o')) || ((arr[1][0] == 'o') && (arr[1][1] == 'o') && (arr[1][2] == 'o')) || ((arr[2][0] == 'o') && (arr[2][1] == 'o') && (arr[2][2] == 'o'))){
  					board.setWinner("O Won!", 170,660,80);
  					break;
  				}
  				else if(((arr[0][0] == 'o') && (arr[1][0] == 'o') && (arr[2][0] == 'o')) || ((arr[0][1] == 'o') && (arr[1][1] == 'o') && (arr[2][1] == 'o')) || ((arr[0][2] == 'o') && (arr[1][2] == 'o') && (arr[2][2] == 'o'))){
   				 board.setWinner("O Won!", 170,660,80);
  					break;
  				}
  				else if(((arr[0][0] == 'o') && (arr[1][1] == 'o') && (arr[2][2] == 'o')) || ((arr[0][2] == 'o') && (arr[1][1] == 'o') && (arr[2][0] == 'o'))){
   				 board.setWinner("O Won!", 170,660,80);
  					break;
  				}

  				//

  				if(((arr[0][0] == 'x') && (arr[0][1] == 'x') && (arr[0][2] == 'x')) || ((arr[1][0] == 'x') && (arr[1][1] == 'x') && (arr[1][2] == 'x')) || ((arr[2][0] == 'x') && (arr[2][1] == 'x') && (arr[2][2] == 'x'))){
   				 board.setWinner("X Won!", 170,660,80);
  					break;
  				}
  				else if(((arr[0][0] == 'x') && (arr[1][0] == 'x') && (arr[2][0] == 'x')) || ((arr[0][1] == 'x') && (arr[1][1] == 'x') && (arr[2][1] == 'x')) || ((arr[0][2] == 'x') && (arr[1][2] == 'x') && (arr[2][2] == 'x'))){
   				 board.setWinner("X Won!", 170,660,80);
  					break;
  				}
  				else if(((arr[0][0] == 'x') && (arr[1][1] == 'x') && (arr[2][2] == 'x')) || ((arr[0][2] == 'x') && (arr[1][1] == 'x') && (arr[2][0] == 'x'))){
   				 board.setWinner("X Won!", 170,660,80);
  					break;
  				}

  				//

  				//


  				if(((arr[0][0] == 'o') && (arr[0][1] == 'o') && (arr[0][2] == 'o')) || ((arr[1][0] == 'o') && (arr[1][1] == 'o') && (arr[1][2] == 'o')) || ((arr[2][0] == 'o') && (arr[2][1] == 'o') && (arr[2][2] == 'o'))){
   				 board.setWinner("O Won!", 170,660,80);
  					break;
  				}
  				else if(((arr[0][0] == 'o') && (arr[1][0] == 'o') && (arr[2][0] == 'o')) || ((arr[0][1] == 'o') && (arr[1][1] == 'o') && (arr[2][1] == 'o')) || ((arr[0][2] == 'o') && (arr[1][2] == 'o') && (arr[2][2] == 'o'))){
   				 board.setWinner("O Won!", 170,660,80);
  					break;
  				}
  				else if(((arr[0][0] == 'o') && (arr[1][1] == 'o') && (arr[2][2] == 'o')) || ((arr[0][2] == 'o') && (arr[1][1] == 'o') && (arr[2][0] == 'o'))){
   				 board.setWinner("O Won!", 170,660,80);
  					break;
  				}

  				//

  				if(((arr[0][0] == 'x') && (arr[0][1] == 'x') && (arr[0][2] == 'x')) || ((arr[1][0] == 'x') && (arr[1][1] == 'x') && (arr[1][2] == 'x')) || ((arr[2][0] == 'x') && (arr[2][1] == 'x') && (arr[2][2] == 'x'))){
   				 board.setWinner("X Won!", 170,660,80);
  					break;
  				}
  				else if(((arr[0][0] == 'x') && (arr[1][0] == 'x') && (arr[2][0] == 'x')) || ((arr[0][1] == 'x') && (arr[1][1] == 'x') && (arr[2][1] == 'x')) || ((arr[0][2] == 'x') && (arr[1][2] == 'x') && (arr[2][2] == 'x'))){
   				 board.setWinner("X Won!", 170,660,80);
  					break;
  				}
  				else if(((arr[0][0] == 'x') && (arr[1][1] == 'x') && (arr[2][2] == 'x')) || ((arr[0][2] == 'x') && (arr[1][1] == 'x') && (arr[2][0] == 'x'))){
   				 board.setWinner("X Won!", 170,660,80);
  					break;
  				}


  			if(arr[0][0] != '-' && arr[0][1] != '-' && arr[0][2] != '-' && arr[1][0] != '-' && arr[1][1] != '-' && arr[1][2] != '-' && arr[2][0] != '-' && arr[2][1] != '-' && arr[2][2] != '-'){
   				 board.setWinner("TIE!", 170,660,80);
  					board.showText(true);
  					break;
				}

				board.showText(true);
board.repaint();


}
break;

}
}

}

//2player
//player1



if(g1==2){



//***Not Printing

	boolean turn2 = true;
	boolean turn1 = true;
							  System.out.print("Enter player 1's name:");
							  String u = reader.nextLine();
								reader.nextLine();

							  System.out.print("Enter player 2's name:");
					  String z = reader.nextLine();

for(int x = 0; x < 9; x++){


	   					while(turn1 == true){
	   					System.out.print("  1: What row would you like to choose?");
	  		  			int q = reader.nextInt();

					while(q>2||q<0){
					System.out.println("\n Enter a number 0-2");
					 q = reader.nextInt();
					}


					System.out.print("1: What coloumn would you like to choose?");
					int w = reader.nextInt();

						while(w>2||w<0){
						System.out.println("\n Enter a number 0-2");
						 w = reader.nextInt();
					}



						if(arr[q][w]=='-'){
						 arr[q][w]='x';
						 board.repaint();
						 turn1 = false;
						 turn2 = true;
						}

						else{
							System.out.println("Pick an open spot!\n\n");
						}


	//player 2

									while(turn2 == true){
					   					System.out.print("  2: What row would you like to choose?");
					  		  			int v = reader.nextInt();

											while(v>2||v<0){
											System.out.println("\n Enter a number 0-2");
											 v = reader.nextInt();
											}


											System.out.print("  2:What coloumn would you like to choose?");
											int n = reader.nextInt();

												while(v>2||v<0){
												System.out.println("\n Enter a number 0-2");
												 n = reader.nextInt();
											}



										if(arr[v][n]=='-'){
										 arr[v][n]='o';
										 board.repaint();
										 turn2 = false;
										 turn1 = true;
										}

										else{
											System.out.println("Pick an open spot!\n\n");
										}


//wins

 				if(((arr[0][0] == 'o') && (arr[0][1] == 'o') && (arr[0][2] == 'o')) || ((arr[1][0] == 'o') && (arr[1][1] == 'o') && (arr[1][2] == 'o')) || ((arr[2][0] == 'o') && (arr[2][1] == 'o') && (arr[2][2] == 'o'))){
  					board.setWinner("O Won!", 170,660,80);
  					x=9;
  					break;
  				}
  				else if(((arr[0][0] == 'o') && (arr[1][0] == 'o') && (arr[2][0] == 'o')) || ((arr[0][1] == 'o') && (arr[1][1] == 'o') && (arr[2][1] == 'o')) || ((arr[0][2] == 'o') && (arr[1][2] == 'o') && (arr[2][2] == 'o'))){
   				 board.setWinner("O Won!", 170,660,80);
  					x=9;
  					break;
  				}
  				else if(((arr[0][0] == 'o') && (arr[1][1] == 'o') && (arr[2][2] == 'o')) || ((arr[0][2] == 'o') && (arr[1][1] == 'o') && (arr[2][0] == 'o'))){
   				 board.setWinner("O Won!", 170,660,80);
  					x=9;
  					break;
  				}

  				//

  				if(((arr[0][0] == 'x') && (arr[0][1] == 'x') && (arr[0][2] == 'x')) || ((arr[1][0] == 'x') && (arr[1][1] == 'x') && (arr[1][2] == 'x')) || ((arr[2][0] == 'x') && (arr[2][1] == 'x') && (arr[2][2] == 'x'))){
   				 board.setWinner("X Won!", 170,660,80);

  					x=9;
  					break;
  				}
  				else if(((arr[0][0] == 'x') && (arr[1][0] == 'x') && (arr[2][0] == 'x')) || ((arr[0][1] == 'x') && (arr[1][1] == 'x') && (arr[2][1] == 'x')) || ((arr[0][2] == 'x') && (arr[1][2] == 'x') && (arr[2][2] == 'x'))){
   				 board.setWinner("X Won!", 170,660,80);
  					x=9;
  					break;
  				}
  				else if(((arr[0][0] == 'x') && (arr[1][1] == 'x') && (arr[2][2] == 'x')) || ((arr[0][2] == 'x') && (arr[1][1] == 'x') && (arr[2][0] == 'x'))){
   				 board.setWinner("X Won!", 170,660,80);

  					x=9;
  					break;
  				}

  				//

  				//


  				if(((arr[0][0] == 'o') && (arr[0][1] == 'o') && (arr[0][2] == 'o')) || ((arr[1][0] == 'o') && (arr[1][1] == 'o') && (arr[1][2] == 'o')) || ((arr[2][0] == 'o') && (arr[2][1] == 'o') && (arr[2][2] == 'o'))){
   				 board.setWinner("O Won!", 170,660,80);
  					x=9;
  					break;
  				}
  				else if(((arr[0][0] == 'o') && (arr[1][0] == 'o') && (arr[2][0] == 'o')) || ((arr[0][1] == 'o') && (arr[1][1] == 'o') && (arr[2][1] == 'o')) || ((arr[0][2] == 'o') && (arr[1][2] == 'o') && (arr[2][2] == 'o'))){
   				 board.setWinner("O Won!", 170,660,80);
  					x=9;
  					break;
  				}
  				else if(((arr[0][0] == 'o') && (arr[1][1] == 'o') && (arr[2][2] == 'o')) || ((arr[0][2] == 'o') && (arr[1][1] == 'o') && (arr[2][0] == 'o'))){
   				 board.setWinner("O Won!", 170,660,80);

  					x=9;
  					break;
  				}

  				//

  				if(((arr[0][0] == 'x') && (arr[0][1] == 'x') && (arr[0][2] == 'x')) || ((arr[1][0] == 'x') && (arr[1][1] == 'x') && (arr[1][2] == 'x')) || ((arr[2][0] == 'x') && (arr[2][1] == 'x') && (arr[2][2] == 'x'))){
   				 board.setWinner("X Won!", 170,660,80);

  					x=9;
  					break;
  				}
  				else if(((arr[0][0] == 'x') && (arr[1][0] == 'x') && (arr[2][0] == 'x')) || ((arr[0][1] == 'x') && (arr[1][1] == 'x') && (arr[2][1] == 'x')) || ((arr[0][2] == 'x') && (arr[1][2] == 'x') && (arr[2][2] == 'x'))){
   				 board.setWinner("X Won!", 170,660,80);

  					x=9;
  					break;
  				}
  				else if(((arr[0][0] == 'x') && (arr[1][1] == 'x') && (arr[2][2] == 'x')) || ((arr[0][2] == 'x') && (arr[1][1] == 'x') && (arr[2][0] == 'x'))){
   				 board.setWinner("X Won!", 170,660,80);
  					x=9;
  					break;
  				}


  			if(arr[0][0] != '-' && arr[0][1] != '-' && arr[0][2] != '-' && arr[1][0] != '-' && arr[1][1] != '-' && arr[1][2] != '-' && arr[2][0] != '-' && arr[2][1] != '-' && arr[2][2] != '-'){
   				 board.setWinner("TIE!", 170,660,80);
  					x=9;

  					break;
				}




board.showText(true);
board.repaint();
}

break;
}

}
}
}
}




















