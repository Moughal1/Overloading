# Overloading
#include&lt;iostream.h> 
#include&lt;conio.h>
#include&lt;process.h>
class distance 
{
private: 
int feet; 
float inches;
public:
distance(): feet(0), inches(0.0){}
distance(int ft, float in): feet(ft), inches(in){}
void getdistance()
{
cout&lt;&lt;"enter the feet value";
cin>>feet;
cout&lt;&lt;"enter the inches value";
cin>>inches; 
}
void showdistance() const 
{
cout&lt;&lt;feet&lt;&lt;"\'-"&lt;&lt;inches&lt;&lt;'\"'; 
}
distance operator - (distance) ;
};
distance distance::operator -(distance d2)
{
int obj1=feet*12+inches;
int obj2=d2.feet*12+d2.inches;
if(obj1&lt;obj2) 
{
cout&lt;&lt;"Subtraction Not Possible"; 
exit (1); 
}
else 
{
feet -  d2.feet; inches - d2.inches ; 
}
if(inches>=12.0) 
{
inches-=12.0; feet++; 
}
return distance(obj1,obj2);
}
int main()
{
clrscr();
distance d1,d3;
distance d2(11,6.25);
d1.getdistance();
d3=d1-d2;
cout&lt;&lt;"d1 ="; 
d1.showdistance(); 
cout&lt;&lt;endl; 
cout&lt;&lt;"d2 =";
d2.showdistance(); 
cout&lt;&lt;endl;
cout&lt;&lt;"d3 =";
d3.showdistance();
cout&lt;&lt;endl;
return 0;
}
