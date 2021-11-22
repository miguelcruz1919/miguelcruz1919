- 👋 Hi, I’m @miguelcruz1919
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...

<!---
miguelcruz1919/miguelcruz1919 is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->


#include <iostream>
#include <cstdlib>
#include <time.h>
#include <windows.h>
#include <conio.h>
#define FIL 20
#define COL 50
using namespace std;
int destinox, puntox, puntoy;
char lab[FIL][COL];
void Inicializar();
void Imprimir();
void GenerarCamino(int i, int j);
void GenerarParedes();
void FinGenerar();
void Jugar(int tecla);
using namespace std;

int main(int argc, char** argv) {
	srand(unsigned(time(NULL)));
    Inicializar();
    int x=1+rand()%FIL-2;
    GenerarCamino(x, 1);
    lab[x][1]='I';
    GenerarParedes();
    FinGenerar();
    Imprimir();
    int tecla;
    puntox=x;
    puntoy=1;
    while(true){
    	tecla=getch();
    	if(tecla==27) break;
    	else{
    		
    		Jugar(tecla);
    		if(lab[puntox][puntoy+1]=='F'){
    			cout<<"Felicidades! llegaste a la salida :)"<<endl;
    			break;
    		}
    		
    	}
    	
    }
    
	system("pause");
	return 0;
}

void Inicializar(){
     for(int i=0; i<FIL; i++)
     {
             for(int j=0; j<COL; j++)
             {
                     if(i==0 || j==0 || i==FIL-1 || j==COL-1) lab[i][j]='P';
                     else lab[i][j]=' ';
                     }
             }
     }
