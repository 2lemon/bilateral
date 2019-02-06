#include <stdio.h>
#include <iostream>
#include <stdlib.h>

using namespace std;
void newvalue(int i,int j);                     //declare the function

int Imageout[375][500][3];                //declare a new arrary  CMY color space
int Imagenew[375][500][3];                //declare a new arrary
char cube[375][500];                    //conditions for 6 cubes

int main(int argc, char *argv[])

{
    // Define file pointer and variables
    FILE *file;
    int BytesPerPixel;
    int SizeCo;
    int SizeRo;
    int Size = 256;
    
    // Check for proper syntax
    if (argc < 3){
        cout << "Syntax Error - Incorrect Parameter Usage:" << endl;
        cout << "program_name input_image.raw output_image.raw [BytesPerPixel = 1] [Size = 256]" << endl;
        return 0;
    }
    
    // Check if image is grayscale or color
    if (argc < 4){
        BytesPerPixel = 1; // default is grey image
    }
    else {
        BytesPerPixel = atoi(argv[3]);
        // Check if size is specified
        if (argc >= 5){
            SizeCo = atoi(argv[4]);
            SizeRo = atoi(argv[5]);
        }
    }
    
    // Allocate image data array
    unsigned char Imagedata[SizeRo][SizeCo][BytesPerPixel];
    
    // Read image (filename specified by first argument) into image data matrix
    if (!(file=fopen(argv[1],"rb"))) {
        cout << "Cannot open file: " << argv[1] <<endl;
        exit(1);
    }
    fread(Imagedata, sizeof(unsigned char), SizeRo*SizeCo*BytesPerPixel, file);
    fclose(file);
    
    ///////////////////////// INSERT YOUR PROCESSING CODE HERE /////////////////////////
    //int Imageout[SizeRo][SizeCo][3];                //declare a new arrary  CMY color space
    //int Imagenew[SizeRo][SizeCo][3];                 //declare a new arrary
    unsigned char Image_final[SizeRo][SizeCo][3];   //declare the output arrary
    int i,j,k = 0;                                  //couting index
    double F[3][3]= {{0,0,0},{0,0,7.0/16.0},{3.0/16.0,5.0/16.0,1.0/16.0}};    //declare F matrix
    double F_r[3][3] = {{0,0,0},{7.0/16.0,0,0},{1.0/16.0,5.0/16.0,3.0/16.0}}; //declare F inver matrix
    double T = 127.0;                                 //declare thresholding
    int Error[3];                               //declare error
    int Value;                                  //Given value
    //copy information to new array
    for(k = 0 ; k < 3 ; k++){
        for (i = 0; i < SizeRo ; i++) {
            for (j = 0; j< SizeCo; j++) {
                Imagenew[i][j][k] = Imagedata[i][j][k];
            }
        }
    }

    //cubes determind
    for(i = 0;i < SizeRo;i++ ){
        for(j = 0;j < SizeCo; j++){
            if((Imagenew[i][j][0]+Imagenew[i][j][1]) > 255 ){
                    if((Imagenew[i][j][1]+Imagenew[i][j][2]) > 255) {
                        if ((Imagenew[i][j][0] + Imagenew[i][j][1] + Imagenew[i][j][2]) > 510) {
                            cube[i][j] = 'a';
                        } else {
                            cube[i][j] = 'b';
                        }
                    }
                    else{
                        cube[i][j] = 'c';
                    }
           }
            else{
                if(!((Imagenew[i][j][1]+Imagenew[i][j][2]) > 255)){
                    if(!((Imagenew[i][j][0] + Imagenew[i][j][1] + Imagenew[i][j][2]) > 255)){
                        cube[i][j] = 'd';
                    }
                    else{
                        cube[i][j] = 'e';
                    }
                }
                else{
                        cube[i][j] = 'f';
                }
            }
        }
    }


    for (i = 0; i < SizeRo; i++) {
        if (i%2 == 0) {                                     //forward
            for (j = 0; j < SizeCo; j++) {
                        newvalue(i,j);
                        Error[0] = Imagenew[i][j][0] - (255-Imageout[i][j][0]);
                        Error[1] = Imagenew[i][j][1] - (255-Imageout[i][j][1]);
                        Error[2] = Imagenew[i][j][2] - (255-Imageout[i][j][2]);
                
                if (j < 499) {                  //SPECIAL
                    Imagenew[i][j + 1][0] = Imagenew[i][j + 1][0] + (7.0 / 16.0) * Error[0];
                    Imagenew[i][j + 1][1] = Imagenew[i][j + 1][1] + (7.0 / 16.0) * Error[1];
                    Imagenew[i][j + 1][2] = Imagenew[i][j + 1][0] + (7.0 / 16.0) * Error[2];
                }
                if((j<499)&& (i<374)){
                    Imagenew[i + 1][j + 1][0] = Imagenew[i + 1][j + 1][0] + (1.0 / 16.0) * Error[0];
                    Imagenew[i + 1][j + 1][1] = Imagenew[i + 1][j + 1][1] + (1.0 / 16.0) * Error[1];
                    Imagenew[i + 1][j + 1][2] = Imagenew[i + 1][j + 1][2] + (1.0 / 16.0) * Error[2];
                }
                if ((j > 0) && (i < 374)) {
                    Imagenew[i + 1][j - 1][0] = Imagenew[i + 1][j - 1][0] + (3.0 / 16.0) * Error[0];
                    Imagenew[i + 1][j - 1][1] = Imagenew[i + 1][j - 1][1] + (3.0 / 16.0) * Error[1];
                    Imagenew[i + 1][j - 1][2] = Imagenew[i + 1][j - 1][2] + (3.0 / 16.0) * Error[2];
                }
                if(i < 374) {
                    Imagenew[i + 1][j][0] = Imagenew[i + 1][j][0] + (5.0 / 16.0) * Error[0];
                    Imagenew[i + 1][j][1] = Imagenew[i + 1][j][1] + (5.0 / 16.0) * Error[1];
                    Imagenew[i + 1][j][2] = Imagenew[i + 1][j][2] + (5.0 / 16.0) * Error[2];
                }
                Error[0] = 0;
                Error[1] = 0;
                Error[2] = 0;
            }
        }
        else if (i%2 == 1) {    //backward
            
            for (j = 499 ; j >= 0 ; j-- ) {
                    newvalue(i,j);
                    Error[0] = Imagenew[i][j][0] - (255-Imageout[i][j][0]);
                    Error[1] = Imagenew[i][j][1] - (255-Imageout[i][j][1]);
                    Error[2] = Imagenew[i][j][2] - (255-Imageout[i][j][2]);

                if(j > 0 ){
                    Imagenew[i][j-1][0] = Imagenew[i][j-1][0] + (7.0/16.0)*Error[0];
                    Imagenew[i][j-1][1] = Imagenew[i][j-1][1] + (7.0/16.0)*Error[1];
                    Imagenew[i][j-1][2] = Imagenew[i][j-1][2] + (7.0/16.0)*Error[2];
                }
                if(i < 374) {
                    Imagenew[i+1][j][0] = Imagenew[i+1][j][0] + (5.0/16.0) * Error[0];
                    Imagenew[i+1][j][1] = Imagenew[i+1][j][1] + (5.0/16.0) * Error[1];
                    Imagenew[i+1][j][2] = Imagenew[i+1][j][2] + (5.0/16.0) * Error[2];
                }
                if((j > 0) && (i < 374)){
                    Imagenew[i+1][j-1][0] = Imagenew[i+1][j-1][0] + (1.0/16.0)*Error[0];
                    Imagenew[i+1][j-1][1] = Imagenew[i+1][j-1][1] + (1.0/16.0)*Error[1];
                    Imagenew[i+1][j-1][2] = Imagenew[i+1][j-1][2] + (1.0/16.0)*Error[2];
                }
                if((i < 374)&&( j < 499)){
                    Imagenew[i+1][j+1][0] = Imagenew[i+1][j+1][0] + (3.0/16.0)* Error[0];
                    Imagenew[i+1][j+1][1] = Imagenew[i+1][j+1][1] + (3.0/16.0)* Error[1];
                    Imagenew[i+1][j+1][2] = Imagenew[i+1][j+1][2] + (3.0/16.0)* Error[2];
                }
                Error[0] = 0;
                Error[1] = 0;
                Error[2] = 0;
            }
        }
    }
    //write the output
    for (i = 0; i < SizeRo ; i++) {
        for (j = 0; j < SizeCo; j++) {
            for (k = 0; k < 3; k++) {
                Image_final[i][j][k] = (unsigned char)Imageout[i][j][k];
            }
        }
    }
    
    
    
    // Write image data (filename specified by second argument) from image data matrix
    if (!(file=fopen(argv[2],"wb"))) {
        cout << "Cannot open file: " << argv[2] << endl;
        exit(1);
    }
    fwrite(Image_final,sizeof(unsigned char), (SizeCo)*(SizeRo)*3, file);
    fclose(file);
    
    return 0;
}
//determind the final RGB value
void newvalue(int i,int j){
    //for CMY
    if(cube[i][j] == 'a'){
        Imageout[i][j][0] = 0;
        Imageout[i][j][1] = 0;
        Imageout[i][j][2] = 0;
        if(Imagenew[i][j][2] < 127){
            if(Imagenew[i][j][2] <= Imagenew[i][j][0]){
                if(Imagenew[i][j][2] <= Imagenew[i][j][1]){
                    Imageout[i][j][0] = 0;
                    Imageout[i][j][1] = 0;
                    Imageout[i][j][2] = 255;
                }
            }
        }
        if(Imagenew[i][j][1] < 127){
            if(Imagenew[i][j][1] <= Imagenew[i][j][2]){
                if(Imagenew[i][j][1] <= Imagenew[i][j][0]){
                    Imageout[i][j][0] = 255;
                    Imageout[i][j][1] = 0;
                    Imageout[i][j][2] = 0;
                }
            }
        }
        if(Imagenew[i][j][0] < 127){
            if(Imagenew[i][j][0] <= Imagenew[i][j][2]){
                if(Imagenew[i][j][0] <= Imagenew[i][j][1]){
                    Imageout[i][j][0] = 0;
                    Imageout[i][j][1] = 255;
                    Imageout[i][j][2] = 0;
                }
            }
        }
    }
    //for MYGC
    if(cube[i][j] == 'b'){
        Imageout[i][j][0] = 255;
        Imageout[i][j][1] = 0;
        Imageout[i][j][2] = 0;
        if (Imagenew[i][j][1] >= Imagenew[i][j][2]){
            if(Imagenew[i][j][0] >= Imagenew[i][j][2]){
                if(Imagenew[i][j][0] >= 127){
                    Imageout[i][j][0] = 0;
                    Imageout[i][j][1] = 0;
                    Imageout[i][j][2] = 255;
                }
                else{
                    Imageout[i][j][0] = 0;
                    Imageout[i][j][1] = 255;
                    Imageout[i][j][2] = 255;
                }
            }
        }
        if (Imagenew[i][j][1] >= Imagenew[i][j][0]){
            if(Imagenew[i][j][2] >= Imagenew[i][j][0]){
                if(Imagenew[i][j][2] >= 127){
                    Imageout[i][j][0] = 0;
                    Imageout[i][j][1] = 255;
                    Imageout[i][j][2] = 0;
                }
                else{
                    Imageout[i][j][0] = 0;
                    Imageout[i][j][1] = 255;
                    Imageout[i][j][2] = 255;
                }
            }
        }
    }
    //for RGMY
    if(cube[i][j] == 'c'){
        if(Imagenew[i][j][2] > 127){
            if(Imagenew[i][j][0] > 127){
                if(Imagenew[i][j][2] >= Imagenew[i][j][1]){
                    Imageout[i][j][0] = 255;
                    Imageout[i][j][1] = 0;
                    Imageout[i][j][2] = 0;
                }
                else{
                    Imageout[i][j][0] = 0;
                    Imageout[i][j][1] = 0;
                    Imageout[i][j][2] = 255;
                }
            }
            else{
                if(Imagenew[i][j][1] > (Imagenew[i][j][2] + Imagenew[i][j][0])){
                    Imageout[i][j][0] = 0;
                    Imageout[i][j][1] = 255;
                    Imageout[i][j][2] = 255;
                }
                else{
                    Imageout[i][j][0] = 255;
                    Imageout[i][j][1] = 0;
                    Imageout[i][j][2] = 0;
                }
            }
        }
        else{
            if(Imagenew[i][j][0] >= 127){
                if(Imagenew[i][j][1] >= 127) {
                    Imageout[i][j][0] = 0;
                    Imageout[i][j][1] = 0;
                    Imageout[i][j][2] = 255;
                }
                else{
                    Imageout[i][j][0] = 255;
                    Imageout[i][j][1] = 0;
                    Imageout[i][j][2] = 255;
                }
            }
            else{
                if(Imagenew[i][j][0] >= Imagenew[i][j][1]){
                    Imageout[i][j][0] = 255;
                    Imageout[i][j][1] = 0;
                    Imageout[i][j][2] = 255;
                }
                else{
                    Imageout[i][j][0] = 0;
                    Imageout[i][j][1] = 255;
                    Imageout[i][j][2] = 255;
                }
            }
        }
    }
    //for KRGB
    if(cube[i][j] == 'd'){
        Imageout[i][j][0] = 255;
        Imageout[i][j][1] = 255;
        Imageout[i][j][2] = 255;
        if(Imagenew[i][j][2] > 127){
            if(Imagenew[i][j][2] >= Imagenew[i][j][0]){
                if(Imagenew[i][j][2] >= Imagenew[i][j][1]){
                    Imageout[i][j][0] = 255;
                    Imageout[i][j][1] = 255;
                    Imageout[i][j][2] = 0;
                }
            }
        }
        if(Imagenew[i][j][1] > 127){
            if(Imagenew[i][j][1] >= Imagenew[i][j][2]){
                if(Imagenew[i][j][1] >= Imagenew[i][j][0]){
                    Imageout[i][j][0] = 0;
                    Imageout[i][j][1] = 255;
                    Imageout[i][j][2] = 255;
                }
            }
        }
        if(Imagenew[i][j][0] > 127){
            if(Imagenew[i][j][0] >= Imagenew[i][j][2]){
                if(Imagenew[i][j][0] >= Imagenew[i][j][1]){
                    Imageout[i][j][0] = 255;
                    Imageout[i][j][1] = 0;
                    Imageout[i][j][2] = 255;
                }
            }
        }
    }
    //for RGBM
    if(cube[i][j] == 'e') {
        Imageout[i][j][0] = 0;
        Imageout[i][j][1] = 255;
        Imageout[i][j][2] = 255;
        if (Imagenew[i][j][0] > Imagenew[i][j][1]) {
            if (Imagenew[i][j][0] >= Imagenew[i][j][2]) {
                if (Imagenew[i][j][2] < 127) {
                    Imageout[i][j][0] = 255;
                    Imageout[i][j][1] = 0;
                    Imageout[i][j][2] = 255;
                } else {
                    Imageout[i][j][0] = 255;
                    Imageout[i][j][1] = 0;
                    Imageout[i][j][2] = 0;
                }
            }
        }
        if (Imagenew[i][j][2] > Imagenew[i][j][1]) {
            if (Imagenew[i][j][2] >= Imagenew[i][j][0]) {
                if (Imagenew[i][j][0] < 127) {
                    Imageout[i][j][0] = 255;
                    Imageout[i][j][1] = 255;
                    Imageout[i][j][2] = 0;
                } else {
                    Imageout[i][j][0] = 255;
                    Imageout[i][j][1] = 0;
                    Imageout[i][j][2] = 0;
                }
            }
        }
    }
    //for CMGB
    if(cube[i][j] == 'f'){
        if(Imagenew[i][j][2] > 127){
            if(Imagenew[i][j][0] > 127){
                if(Imagenew[i][j][1] >= Imagenew[i][j][0]){
                    Imageout[i][j][0] = 0;
                    Imageout[i][j][1] = 255;
                    Imageout[i][j][2] = 0;
                }
                else{
                    Imageout[i][j][0] = 255;
                    Imageout[i][j][1] = 0;
                    Imageout[i][j][2] = 0;
                }
            }
            else{
                if(Imagenew[i][j][1] > 127){
                    Imageout[i][j][0] = 0;
                    Imageout[i][j][1] = 255;
                    Imageout[i][j][2] = 0;
                }
                else{
                    Imageout[i][j][0] = 255;
                    Imageout[i][j][1] = 255;
                    Imageout[i][j][2] = 0;
                }
            }
        }
        else{
            if(Imagenew[i][j][0] > 127){
                if((Imagenew[i][j][0] - Imagenew[i][j][1] + Imagenew[i][j][2]) >= 127){
                    Imageout[i][j][0] = 255;
                    Imageout[i][j][1] = 0;
                    Imageout[i][j][2] = 0;
                }
                else{
                    Imageout[i][j][0] = 0;
                    Imageout[i][j][1] = 255;
                    Imageout[i][j][2] = 255;
                }
            }
            else{
                if(Imagenew[i][j][1] >= Imagenew[i][j][2]){
                    Imageout[i][j][0] = 0;
                    Imageout[i][j][1] = 255;
                    Imageout[i][j][2] = 255;
                }
                else{
                    Imageout[i][j][0] = 255;
                    Imageout[i][j][1] = 255;
                    Imageout[i][j][2] = 0;
                }
            }
        }
    }

}
