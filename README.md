# buy-and-sell-stock
#include<iostream>
using namespace std;
int main()
{
	int a[10];
	int i,j,n;
	cout<<"enter a no size:";
	cin>>n;
	cout<<"enter stock rate:\n";
	for(i=0;i<n;i++)
	 cin>>a[i];
	 
//	cout<<"given stock are\n";
	for(i=0;i<n;i++)
	 cout<<a[i]<<" ";
	int buy_day=0,sell_day,profit=0,cpro=0,tolpro=0;
	for(i=0;i<n-1;i++)
	{	cout<<"i="<<i<<"\n";
		if(a[i+1]>a[buy_day])
		{
	//	cout<<"stock is greater"<<"\n";	
		cpro=a[i+1]-a[buy_day];
		if(cpro>profit)
		  {
		   profit=cpro;
		//   cout<<"profit is "<<profit<<"\n";	
		   sell_day=i+1;
		 //  cout<<"sell day is"<<sell_day<<"\n";	
	      }
		}
		else 
		{   tolpro+=profit;
		//	cout<<"since sell stock profit is less total profit is"<<tolpro<<"\n";	
		    if(tolpro>0)
			   cout<<"\n"<<"buy day is "<<buy_day<<"sell day is "<<sell_day;
			
			buy_day=i+1;
		//	cout<<"next stock buy day is "<<buy_day<<"\n";	
		    profit=0;
			cpro=0;
		}
	}
	tolpro+=profit;
//	cout<<"lop ended tolprofit is "<<tolpro<<"\n";	
	if(tolpro>0)
	{	
	cout<<"\n"<<"buy day is "<<buy_day<<"sell day is "<<sell_day;
	cout<<"\ntotal profit is"<<tolpro;
	}
	else
	 cout<<"\nprofit os zero ";
	return 0;
}
