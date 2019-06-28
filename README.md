#include <iostream>
#include <fstream>
using namespace std;

int main()
{ int r,c,t[20][20];
    ifstream fileinput;
    fileinput.open("input.txt");
    fileinput>>r>>c;
   
    int **array;
    array=new int*[r];
    for(int i=0;i<r;i++)
    {
        array[i]=new int[c];
    }
    ofstream fileoutput;
    fileoutput.open("output.txt");
    
    for (int i=0;i<r;i++){
    for (int j=0;j<c;j++)
    {
        
        fileinput>>array[i][j];
         t[j][i] = array[i][j]; //changign row & column
    }
        
    }
    for(int i=0;i<c;i++) //row will become column
    {
    for(int j=0;j<r;j++) //column will become row
    {
     
      fileoutput<<t[i][j]<<" ";
     if(j==r-1)  //column is less than row
        fileoutput<<endl;
    }
   
  }
}
