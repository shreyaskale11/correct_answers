Q1
2.0/2.0 points (graded)
Consider the following program

#include
using namespace std;

class Human{
protected:
int age;
int height;

public:
	Human(int height, int age){
		this->height = height;
		this->age = age;
	}

	int getAge(){
		return age;		
	}

	int getHeight(){
		return height;
	}
};

class Boy: public Human{
public:
Boy(int height, int age): Human(height, age) {}
int getHeight(){
return height+5;
}
};

class Girl: public Human{
public:
Girl(int height, int age): Human(height, age) {}
int getAge(){
return age-2;
}
};

int main(){

Boy b(94,37);
Girl g(94, 37);
Human h(94, 37);

cout << b.getAge() +
	  b.getHeight() +
	  g.getAge() +
	  g.getHeight() + 
	  h.getAge() +
	  h.getHeight();

return 0;
}
What is the output of above program?

396
correct
SubmitYou have used 1 of 1 attemptSome problems have options such as save, reset, hints, or show answer. These options follow the Submit button.

Show Answer
Q2
2.0/2.0 points (graded)
A parallelepiped is a three-dimensional figure formed by six parallelograms. Let a, b, and c be the basis vectors defining a three-dimensional parallelepiped. Volume of a parallelepiped is given by the scalar triple product.
Vparallelepiped=|a.(bxc)|

struct V3 {
  double x, y, z;
  double dot(V3 b){
    double ans;
    ans=x*b.x+y*b.y+z*b.z;
    return ans;
  }

  V3 cross(V3 b){
  V3 v;
  v.x=y*b.z-z*b.y;
  v.y=z*b.x-x*b.z;
  v.z=x*b.y-y*b.x;
  return v;
  }

};

struct parallelepiped{
    V3 a,b,c;
    double Volume(){
        double ans;
        line 1
        if(ans<0) ans=-ans;
        return ans;
    }
}
int main(){
    V3 v1, v2, v3;
    v1.x=3;
    v1.y=13;
    v1.z=12;
    v2.x=5;
    v2.y=8;
    v2.z=8;
    v3.x=11;
    v3.y=13;
    v3.z=3;

    parallelepiped p;
    p.a=v1;
    p.b=v2;
    p.c=v3;

    double Volume;
    Volume=p.Volume();

    cout<<Volume;
	return 0;
 }
What should be written instead of line 1 to get correct Volume of the parallelepiped?

ans=a.cross(b.dot(c));
ans=a.dot(b, cross(c));
ans=dot(a, cross(b, c))
ans=a.dot(b.cross(c)); correct

What is the volume of the given parallelepiped?

732
433 correct
2928
1465
SubmitYou have used 1 of 2 attemptsSome problems have options such as save, reset, hints, or show answer. These options follow the Submit button.

SaveSave Your Answer
Show Answer
Q3
0.0/1.0 point (graded)
Consider the following C++ program with unspecified expressions Expr1 and Expr2

#include <iostream>
#include
using namespace std;

struct A{
int x;
int y;
int z;
};

struct A* D(int x, int y, int z){
Expr1
(C).x=xy;
(C).y=yz;
(C).z=xz;
return C;
}

int main(){
int a=2, b=3, c=4;
Expr2
E = D(a, b, c);
}

Expressions Expr1 and Expr2 need to be identified, such that the value of '(*E).x', '(*E).y', and '(*E).z' are 6, 12, and 8 respectively. Select an appropriate choice from the following:

Expr1 is required to be replaced by struct A* C; and Expr2 by struct A* E;
Expr1 is required to be replaced by struct A* C; and Expr2 by struct A* E = (struct A*) malloc(sizeof(struct A));
Expr1 is required to be replaced by struct A* C = (struct A*) malloc(sizeof(struct A)); and Expr2 by struct A* E; correct
None of these
SubmitYou have used 1 of 1 attemptSome problems have options such as save, reset, hints, or show answer. These options follow the Submit button.

Show Answer
Q4
2.0/2.0 points (graded)
Consider the following block of code

some useful resources on strings

using namespace std;
string str("Wouldn't be caught dead");
string result;

//STAGE 1
int str_break1= str.find_first_of(" "); //Note: " " not "", there is a space
int str_break2= str.find_last_of(" ")+1;
str= str.substr(str_break2)+str.substr(str_break1,str_break2-str_break1)+str.substr(0,str_break1);
//End of STAGE 1

//STAGE 2
string::const_iterator cit;
int index=0;
for(cit=str.begin(); cit!=str.end(); cit++)
{
result+=toupper(*cit);
if (result.at(index)==' '){result[index]='%';}
index++;
}
// End of STAGE 2

//STAGE 3
result.replace(0,5,"a5y49");
//End of STAGE 3

cout <<result.substr(2,5)<<endl; //Final Result

What is the output of above code block?

y49BE
correct

SubmitYou have used 1 of 1 attemptSome problems have options such as save, reset, hints, or show answer. These options follow the Submit button.

Show Answer
Q5
0.0/2.0 points (graded)
sort(it1, it2)[1] is used to sort elements between two pointers(it1 and it2). std::reverse_iterator [2]produces a new iterator that moves from the end to the beginning of the sequence. And min_element(it1, it2) returns iterator of the smallest element in the given range.

Now consider the following blocks of code.

double arr[] = [74, 14, 18, 69, 26, 22, 13, 85, 13, 69, 23];
vector<double> vec (arr, arr + sizeof(arr) / sizeof(arr[0]));
vector<double> vec2(vec);

vector<double>::iterator min_vec = min_element(vec.begin(), vec.end());
sort(vec.begin(),min_vec);
sort(min_vec, vec.end(), greater<double>());
What is the value of *min_vec?

14

vector<double>::reverse_iterator min_vec2 = min_element(vec2.rbegin(), vec2.rend());
sort(min_vec2, vec2.rend(), greater<double>());
sort(vec2.rbegin(),min_vec2);
What is the value of vec2[9]?

74
