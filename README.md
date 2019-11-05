# RSA-algorithm-using-C-
#include<iostream>
#include<math.h>
 
using namespace std;
 

int gcd(int a, int h)
{
    int temp;
    while(1)
    {
        temp = a%h;
        if(temp==0)
        return h;
        a = h;
#include<iostream>
#include<math.h>
 
using namespace std;
 

int gcd(int a, int h)
{
    int temp;
    while(1)
    {
        temp = a%h;
        if(temp==0)
        return h;
        a = h;
        h = temp;
    }
}
 
int main()
{
    double p ;
    double q ;
    double msg ;
    double e;
    double k;
     cout << "Please enter your Message: ";
     cin >> msg;
     cout << "Please enter your p: ";
     cin >> p;
     cout << "Please enter your q: ";
     cin >> q;
     cout << "Please enter your e: ";
     cin >> e;
     cout << "Please enter your k: ";
     cin >> k;
    
    double n=p*q;
    double count;
    double total = (p-1)*(q-1);
 
    while(e<total)
    {
    count = gcd(e,total);
    
    if(count==1)
        break;
    else
        e++;
    }
 
  
    double d;
    d = (1 + (k*total))/e;
    
    double c = pow(msg,e);
    double m = pow(c,d);
    c=fmod(c,n);
    m=fmod(m,n);
 
    cout<<"Message data = "<<msg;
    cout<<"\n"<<"p = "<<p;
    cout<<"\n"<<"q = "<<q;
    cout<<"\n"<<"n = pq = "<<n;
    cout<<"\n"<<"total = "<<total;

    cout<<"\n"<<"Encrypted data = "<<c;
    cout<<"\n"<<"Original Message sent = "<<msg;
 
    return 0;
}
