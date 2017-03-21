# duoxiangshi
#include<stdio.h>
//typedef struct Node* List;
typedef struct  {
	int zhishu;
	int xishu;
} Node;
int  main() {
	int a = 0, b = 0;	
	scanf("%d", &a);
	Node L1[a];
	for(int i=0;i<a;i++){
		scanf("%d %d",&L1[i].xishu,&L1[i].zhishu);
	} 
	scanf("%d", &b);
	Node L2[b];
	for(int i=0;i<b;i++){
		scanf("%d %d",&L2[i].xishu,&L2[i].zhishu);
	}  //构建结构体数组L1，L2 完毕
	int L3[2000]={0};
	for(int i=0;i<a;i++){
		for(int j=0;j<b;j++){
			L3[L1[i].zhishu+L2[j].zhishu]+=(L1[i].xishu*L2[j].xishu);
		}
	}
	int ret=0;
	if(a&&b!=0){
		for(int i=L1[0].zhishu+L2[0].zhishu;i>=0;i--){
		int x;
		x=L3[i];
		if (x){
			printf("%d %d ",L3[i],i);
			ret++;
		}
		}
	}
	
		if(!ret){
			printf("%d %d",0,0); 
		} 
	printf("\n");
	//乘法结束 
	
	int count=0,heng=0;
	int i=0,j=0;
    while(i<a&&j<b){
    	if(L1[i].zhishu>L2[j].zhishu){
    		printf("%d %d ",L1[i].xishu,L1[i].zhishu);
    		i++;
    		count++; 
		}
		else if(L1[i].zhishu==L2[j].zhishu){
			if(L1[i].xishu+L2[j].xishu!=0){
			printf("%d %d ",L1[i].xishu+L2[j].xishu,L1[i].zhishu);
    		count++;
			}
			i++;j++;	
		}
		else {
			printf("%d %d ",L2[j].xishu,L2[j].zhishu);
    		j++;
    		count++;
		}
		heng++;
	}
	
	{
		if (i==a){
    		for(;j<b;j++){
    		printf("%d %d ",L2[j].xishu,L2[j].zhishu);
			}
		}
		else{
    		for(;i<a;i++){
    		printf("%d %d ",L1[i].xishu,L1[i].zhishu);
			}
		}
	} 
	if(heng==0){
		printf("%d %d ",0,0);
	}
    
	//printf("\n");//输出加式结束	
	 
	 

	return 0;
}
