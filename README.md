#include<iostream>
using namespace std;
struct student
{
	char name[30];
	char num[15];
	int age;
	struct student * next;
};

int main()
{
	struct student *p,*q,*head;
	int s;
	int count=0;
	head=NULL;
	while(cout<<"1(input) or 0(end)"<<endl,cin>>s,s==1)
	{
		p=new student;
		cout<<"请输入姓名    ";
		cin>>p->name;
		cout<<"请输入学号    ";
		cin>>p->num;
		cout<<"请输入年龄    ";
		cin>>p->age;
		if(head==NULL)
		{
			head=p;
		}
		else
		{
			q->next=p;
		}
		q=p;
		p->next=NULL;
		count++;	 
	}
	p=head;
	while(p!=NULL)
	{
		cout<<p->name<<" "<<p->num<<" "<<p->age<<endl;
		p=p->next;
	}
	if(count)
	{
		p=head;
		do
		{
			q=p->next;
			delete p;
			p=q;
		}while(q);
	}
	return 0;
}
