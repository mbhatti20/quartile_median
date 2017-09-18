# quartile_median
finding quartiles of an unordered list or array.
#include<iostream>
#include<cmath>
#include<algorithm>
using namespace std;
int median(int A[],int n)
{	int med;
	if(n%2==0)
	{
		return med=((A[n/2-1]+A[n/2])/2.0);
	}
	 else
	{
		return med=(A[n/2]);
	}
}
void quartile(int A[],int n)
{	int Q2,Q1,Q3;
	int LH[n/2],UH[n/2];
	sort(A,A+n);
	if(n%2==0)
	{
		for(int i=0;i<n/2;i++)
		{
			 LH[i]=A[i];
			 UH[i]=A[n/2+i];
			 Q2=median(A,n);
			 Q1=median(LH,n/2);
			 Q3=median(UH,n/2);
		}
	}
	 if(n%2!=0)
		{	Q2=median(A,n);
				for(int i=0;i<n/2;i++)
			{
				 LH[i]=A[i];
				 UH[i]=A[n/2+i+1];
			}	
			Q1=median(LH,n/2);
			Q3=median(UH,n/2);
		}cout<<Q1<<'\n'<<Q2<<'\n'<<Q3;
}
int main()
{   int n;
    cin>>n;
    int A[n];
    for(int i=0;i<n;i++)
    {
        cin>>A[i];
    }

	quartile(A,n);
	
}
