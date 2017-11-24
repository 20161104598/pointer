#include"iostream"
using namespace std;
struct student
{
	char name[50];
	char num[15];
	int age;
	struct student * next;
};

int main()
{
	struct student *p,*q,*head;
	int s=1;
	head=new student;
	q=head;
	p=q;
	cout<<"NAME:";
	cin>>p->name;
	cout<<"NUMBER:";
	cin>>p->num;
	cout<<"AGE:";
	cin>>p->age;
	while(cout<<"1 or 2"<<endl,cin>>s,s==1)
	{
		p=new student;
		q->next=p;
		q=p;
		cout<<"NAME:";
		cin>>p->name;
		cout<<"NUMBER:";
		cin>>p->num;
		cout<<"AGE:";
		cin>>p->age;
		p->next=NULL;	 
	}
	p=head;
	while(p!=NULL)
	{
		cout<<p->name<<"	"<<p->num<<"	"<<p->age<<endl;
		p=p->next;
	}
	p=head;
	do
	{
		q=p->next;
		delete p;
		p=q;
	}while(q);
	return 0;
}

