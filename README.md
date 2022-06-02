#include <iostream>
using namespace std;

//#define KEY_UP 72
//#define KEY_DOWN 80
//#define KEY_LEFT 75
//#define KEY_RIGHT 77

int main() {
    
    int panjangRuang = 20;
    int lebarRuang = 16; 
    
    int posisiKarakterY = 15;
    int posisiKarakterX = 4;
        
    int peta[lebarRuang][panjangRuang] = {
        {8,8,8,8,8,8,1,1,1,1,1,1,1,1,1,1,1,1,1,1},
        {8,8,8,8,8,8,1,1,1,1,1,1,1,5,5,1,1,1,1,1},
        {8,8,8,1,1,1,1,1,1,1,1,1,1,5,5,1,1,1,1,1},
        {8,8,8,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1,1},
        {1,8,8,8,8,8,8,1,1,1,1,1,1,1,1,1,1,1,1,1},
        {1,1,8,8,8,8,8,1,1,1,1,1,1,4,4,4,4,1,1,1},
        {1,1,1,1,1,1,1,1,1,1,1,1,1,4,4,4,4,1,1,1},
        {1,1,1,5,5,1,1,1,1,1,4,4,4,4,4,4,4,1,1,1},
        {1,1,1,5,5,1,1,1,4,4,4,4,4,4,4,4,6,6,6,6},
        {1,1,5,5,1,1,1,1,4,4,4,4,4,4,4,4,4,1,1,1},
        {1,1,5,5,1,1,1,1,4,4,4,1,1,4,4,1,1,1,1,1},
        {1,1,1,1,1,1,1,1,4,4,4,1,1,1,1,1,1,1,1,1},
        {1,1,1,1,1,1,1,1,4,4,4,1,1,1,1,1,1,1,1,1},
        {1,1,1,1,1,1,1,1,1,1,6,1,1,1,1,1,1,1,1,1},
        {1,1,1,1,1,1,1,1,1,1,6,1,1,1,1,1,1,1,1,1},
        {1,1,1,1,1,1,1,1,1,1,6,1,1,1,1,1,1,1,1,1},
    };
    
    //8, 1, 4, 5, 6
    
    
    int arrowKey = 77;
    
    /*
    #define KEY_UP 72
    #define KEY_DOWN 80
    #define KEY_LEFT 75
    #define KEY_RIGHT 77
    */
    
    while(1) {
        // Input Keyboard
        cout << "Masukan perintah\n atas  : 72,\n bawah : 80,\n kiri  : 75,\n kanan : 77\n:";
        cin >> arrowKey;
        cout << "Perintah yang dimasukan " << arrowKey << "\n";
        
        // Aturan menggerakkan karakter ke atas
        if(arrowKey == 72 && (peta[posisiKarakterY-1][posisiKarakterX] == 1) && posisiKarakterY >= 0) {
            // Gerakkan karakter ke atas
            posisiKarakterY = posisiKarakterY-1;
        }
        
        // Aturan menggerakkan karakter ke bawah
        if(arrowKey == 80 && (peta[posisiKarakterY+1][posisiKarakterX] == 1) && posisiKarakterY < lebarRuang) {
            // Gerakkan karakter ke atas
            posisiKarakterY = posisiKarakterY+1;
        }
        
        // Aturan menggerakkan karakter ke kiri
        if(arrowKey == 75 && (peta[posisiKarakterY][posisiKarakterX-1] == 1) && posisiKarakterX >= 0) {
            // Gerakkan karakter ke atas
            posisiKarakterX = posisiKarakterX-1;
        }
        
        // Aturan menggerakkan karakter ke kanan
        if(arrowKey == 77 && (peta[posisiKarakterY][posisiKarakterX+1] == 1) && posisiKarakterX < panjangRuang) {
            // Gerakkan karakter ke atas
            posisiKarakterX = posisiKarakterX+1;
        }
        
        
        //cek obstacle
        if(arrowKey == 72 && arrowKey >= 0) {
        	if(arrowKey == 72 && (peta[posisiKarakterY-1][posisiKarakterX] == 4) && posisiKarakterY >= 0)
            cout << "Kamu menabrak tembok!!\n";
        }
        if(arrowKey == 80 && arrowKey >= 0) {
        	if(arrowKey == 80 && (peta[posisiKarakterY-1][posisiKarakterX] == 4) && posisiKarakterY < lebarRuang)
            cout << "Kamu menabrak tembok!!\n";
        }
        if(arrowKey == 75 && arrowKey >= 0) {
        	if(arrowKey == 75 && (peta[posisiKarakterY-1][posisiKarakterX] == 4) && posisiKarakterY >= 0)
            cout << "Kamu menabrak tembok!!\n";
        }
        if(arrowKey == 77 && arrowKey >= 0) {
        	if(arrowKey == 77 && (peta[posisiKarakterY-1][posisiKarakterX] == 4) && posisiKarakterY < panjangRuang)
            cout << "Kamu menabrak tembok!!\n";
        }
        
        
        
        
        
        
        // Render grafik
        for(int y=0; y<lebarRuang; y++) {
            for(int x=0; x<panjangRuang; x++) {
                
                if(posisiKarakterX == x && posisiKarakterY == y) {
                    cout << 77 << " ";
                } else {
                    cout << peta[y][x] << " ";
                }
            }
            cout << "\n";
        }
    }
     
    
    return 0;
}
