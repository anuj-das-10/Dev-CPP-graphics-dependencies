Instruction for Adding Graphics File in Dev-C++
************************************************************************************************************

1) Copy "graphics.h" and "winbgim.h" files to "include" folder of Dev-Cpp directory.
   Default location is (" C:\Program Files (x86)\Dev-Cpp\MinGW64\include ")


2) Copy "libbgi.a" to file to "lib" folder of Dev-Cpp directory.
   Default location is (" C:\Program Files (x86)\Dev-Cpp\MinGW64\lib ")


Now, 
Open Dev-C++ and go to (Tools > Compiler Options ) then,

1. Compiler set to Configure:  TDM-GCC 4.9.2 32-bit Release    (Select from drop down menu) 
2. Make sure (Add the following commands when calling the linker: ) is checked and append the following:
	
	-lbgi -lgdi32 -lcomdlg32 -luuid -loleaut32 -lole32

3. It will look like this after the previous step: 

	-static-libgcc -lbgi -lgdi32 -lcomdlg32 -luuid -loleaut32 -lole32

4. Press "OK" and you are done!


NOTE:	The graphics.h will work only in the program saved in ".cpp" format.

**************************************************************************************************************

Test your setup with this code: 
-------------------------------------

#include<graphics.h>
int main()
{
    int gd=DETECT,gm;
    initgraph(&gd,&gm,(char *)"");
    circle(200,200,100);
    getch();
    closegraph();
    return 0;
}
