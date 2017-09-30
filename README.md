#include<stdio.h>
#include<stdlib.h>
#define IN 1
#define OUT 0

int main() {
    int state,c,nl,nw,tab,ns,chara;
    nl=nw=tab=ns=chara=0;
    state = OUT;
    while((c = getchar())!= EOF)
    {
     if(isalpha(c))
            chara++;
     if(c == '\n')
        nl++;
     if(c == ' ')
        ns++;
     if(c == '\t')
        tab++;
     if(c == ' ' || c == '\t' || c == '\n')
        state = OUT;
     else if(state == OUT)
     {
         state = IN;
         nw++;
     }

    }
    printf(" space:%d newline:%d tab:%d word:%d characters:%d",ns,nl,tab,nw,chara);

}
