# tic_tac_toe
Game by using simple C++

#include <iostream>
using namespace std;

char player = 'x'; 
int n;
char matrix[3][3]={'1','2','3','4','5','6','7','8','9'};
void draw()
{
   system("cls");
    cout<<"Tic Tac Toe"<<endl;
    for(int i=0; i<3; i++)
    {
        for(int j=0; j<3; j++)
        {
            cout<<matrix[i][j]<<" ";
        }
        cout<<endl;
    }
}

void input()
{
   int a;
   cout<<"It's '"<<player<<"' turn "<<endl<<"Press the no. of the field :";
   cin>>a;

   if(a==1)
   {
     if (matrix[0][0]=='1') 
       matrix[0][0]=player;
     else
     {
       cout<<"Field is already in use.... "<<endl<<"Try again!"<<endl;
       input();
     }
   }

   else if(a==2)
   {
      if(matrix[0][1]=='2')
        matrix[0][1]=player; 
      else
      {
        cout<<"Field is already in use.... "<<endl<<"Try again!"<<endl;
        input();
      }
   } 

   else if(a==3)
   {  
     if(matrix[0][2]=='3')
        matrix[0][2]=player;
      else
      {
        cout<<"Field is already in use.... "<<endl<<"Try again!"<<endl;
        input();
      } 
   }    

   else if(a==4)
   {
     if(matrix[1][0]=='4')
       matrix[1][0]=player;
     else  
     {
      cout<<"Field is already in use.... "<<endl<<"Try again!"<<endl;
      input();
    } 
  }

   else if(a==5)
   {  
     if(matrix[1][1]=='5')
       matrix[1][1]=player;
      else
      {
        cout<<"Field is already in use.... "<<endl<<"Try again!"<<endl;
        input();
      }   
   }   

   else if(a==6)
   {  
      if(matrix[1][2]=='6')
       matrix[1][2]=player;
      else
      {
        cout<<"Field is already in use.... "<<endl<<"Try again!"<<endl;
        input();
      }   
   }

   else if(a==7)
    {  
      if(matrix[2][0]=='7')
         matrix[2][0]=player;
      else 
      {
        cout<<"Field is already in use.... "<<endl<<"Try again!"<<endl;
        input();
      }   
    }

   else if(a==8)
   { 
      if(matrix[2][1]=='8')
       matrix[2][1]=player;
       else
       {
        cout<<"Field is already in use.... "<<endl<<"Try again!"<<endl;
        input();
      }  
   }  

   else if(a==9)
   {
     if(matrix[2][2]=='9')
       matrix[2][2]=player; 
       else{
        cout<<"Field is already in use.... "<<endl<<"Try again!"<<endl;
        input();
      }    
   }  

}

void toggleplayer()
{

    if(player=='x')
      player ='o';
    else 
      player='x';
}

char win()
{     
    //for first plaayer.....

    //for rows
    if (matrix[0][0] =='x' && matrix[0][1] =='x' && matrix[0][2] =='x')
    return 'x';
    if (matrix[1][0] =='x' && matrix[1][1] =='x' && matrix[1][2] =='x')
    return 'x';
    if (matrix[2][0] =='x' && matrix[2][1] =='x' && matrix[2][2] =='x')
    return 'x';

    //for column
    if (matrix[0][0] =='x' && matrix[1][0] =='x' && matrix[2][0] =='x')
    return 'x';
    if (matrix[0][1] =='x' && matrix[1][1] =='x' && matrix[2][1] =='x')
    return 'x';
    if (matrix[0][2] =='x' && matrix[1][2] =='x' && matrix[2][2] =='x')
    return 'x';
    
    //for diagonals
    if (matrix[0][0] =='x' && matrix[1][1] =='x' && matrix[2][2] =='x')
    return 'x';
    if (matrix[0][2] =='x' && matrix[1][1] =='x' && matrix[2][0] =='x')
    return 'x';


    //for second plaayer.....

    //for rows
    if (matrix[0][0] =='o' && matrix[0][1] =='o' && matrix[0][2] =='o')
    return 'o';
    if (matrix[1][0] =='o' && matrix[1][1] =='o' && matrix[1][2] =='o')
    return 'o';
    if (matrix[2][0] =='o' && matrix[2][1] =='o' && matrix[2][2] =='o')
    return 'o';

    //for column
    if (matrix[0][0] =='o' && matrix[1][0] =='o' && matrix[2][0] =='o')
    return 'o';
    if (matrix[0][1] =='o' && matrix[1][1] =='o' && matrix[2][1] =='o')
    return 'o';
    if (matrix[0][2] =='o' && matrix[1][2] =='o' && matrix[2][2] =='o')
    return 'o';
    
    //for diagonals
    if (matrix[0][0] =='o' && matrix[1][1] =='o' && matrix[2][2] =='o')
    return 'o';
    if (matrix[0][2] =='o' && matrix[1][1] =='o' && matrix[2][0] =='o')
    return 'o';

  return '/';  

}


int main()
{
    n = 0;

    while (true)
    { 
        n++;
        draw();
        input();
        draw();

        char result = win();
        if(result == 'x')
        {
            draw();
            cout<<"x wins!..."<<endl;
            exit(0);
        }
        else if(result == 'o')
        {
            draw();
            cout<<"o wins!..."<<endl;
            exit(0);
        }
        else if(result == '/' && n == 9)
        {
            draw();
            cout<<"It is a draw"<<endl;
            exit(0);
        }

        toggleplayer();
    }
    system("pause");
    return 0;
}
