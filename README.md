link-pointers
=============


//
//  main.cpp
//link pointer
//shiyu

#include <iostream>
using namespace std;



struct link
{
    int data;     //data item
    link* next;      //pointer to next link
};

class linklist         //a list of links
{
private:
    link* first;          //pointer to first link
public:
    linklist()
    {first=NULL;}        //no firstlink
    void additem(int d);      //add  data item
    void display();       //display all links
};

//.........................
void linklist::additem(int d)         //add data item
{
    link* newlink= new link;           //make a new link
    newlink->data=d;        //give it data
    newlink->next=first;         //it points to next link
    first=newlink;              //now first pionts to this
    
}
//................................
void linklist::display()         //display all links
{
    link*current=first;
    while(current!=NULL)         // quit on last link
    {
        cout<<current->data<<endl;
        current=current->next;         //movw to next link
        
    }
}

////////////////////////

int main()
{
    linklist li;        //make linked list
    
    li.additem(24);     //add four items
    li.additem(45);
    li.additem(35);
    li.additem(89);
    
    li.display();       //display entire list
    return 0;
}
