#include <stdio.h>
#include <pthread.h>
#include <unistd.h>


int global[2];

void *sum_thread(void *arg) //toplama islemi
{
    int n1,n2,sum;
    n1=global[0];
    n2=global[1];
    sum = n1+n2;

    printf("N1 + N2 = %d\n",sum);

    return NULL;
}

void *sub_thread(void *arg) //cikarma islemi
{
    int n1,n2,sub;
    n1=global[0];
    n2=global[1];
    if(n1>n2){
    	sub = n1-n2;
    }
    else{
    	sub = n2-n1;
    }    

    printf("N1 - N2 = %d\n",sub);

    return NULL;
}

void *mul_thread(void *arg) //carpma islemi
{
    int n1,n2,mul;
    n1=global[0];
    n2=global[1];
    
    mul = n1*n2;
    
    printf("N1 * N2 = %d\n",mul);

    return NULL;
}

void *div_thread(void *arg) //bolme islemi
{
    int n1,n2,div;
    n1=global[0];
    n2=global[1];
    
    div = n1/n2;

    printf("N1 / N2 = %d\n",div);

    return NULL;
}

int main() 
{
    printf("First number: ");
    scanf("%d",&global[0]);

    printf("Second number: ");
    scanf("%d",&global[1]);
    
    pthread_t tid_sum;
    pthread_create(&tid_sum,NULL,sum_thread,global);
    pthread_join(tid_sum,NULL);
    
    pthread_t tid_sub;
    pthread_create(&tid_sub,NULL,sub_thread,global);
    pthread_join(tid_sub,NULL);
    
    pthread_t tid_mul;
    pthread_create(&tid_mul,NULL,mul_thread,global);
    pthread_join(tid_mul,NULL);
    
    pthread_t tid_div;
    pthread_create(&tid_div,NULL,div_thread,global);
    pthread_join(tid_div,NULL);



    return 0;
}
