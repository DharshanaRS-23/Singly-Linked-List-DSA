# Singly-Linked-List-DSA
class Node
{
    int data;
    Node next;
    Node(int data)
    {
        this.data=data;
        this.next=null;
    }
    
}
class SinglyLinkedList
{
    Node head;
    //Insert at begin
    public void InsertAtBegin(int data)
    {
        Node newNode = new Node(data);
        newNode.next = head;
        head = newNode;
    }
    //Insert at end
    public void InsertAtEnd(int data)
    {
        Node newNode = new Node(data);
        Node temp = head;
        while(temp.next!=null)
        {
            temp = temp.next;
        }
        temp.next = newNode;
    }
    //Delete at begin
    public void DeleteAtBegin()
    {
        if(head == null)
        {
            System.out.println("No node to delete");
            return;
        }
        head = head.next;
    }
    //Delete at end
    public void DeleteAtEnd()
    {
        if(head == null)
        {
            System.out.println("List is empty,no node to delete");
            return;
        }
        if(head.next==null)
        {
            head = null;
            return;
        }
        Node temp = head;
        while(temp.next!=null && temp.next.next!=null)
        {
            temp = temp.next;
        }
        temp.next = null;
    }
    //Insert at any position
    public void InsertAtAnyPosition(int position,int data)
    {
        if(position<=0)
        {
            System.out.println("Invalid position");
            return;
        }
        Node newNode = new Node(data);
        if(position==1)
        {
            newNode.next = head;
            head = newNode;
            return;
        }
        Node temp = head;
        for(int i=0;i<position-1;i++)
        {
            temp = temp.next;
        }
        if(temp == null)
        {
            System.out.println("Exceeds the given length");
            return;
        }
        newNode.next = temp.next;
        temp.next = newNode;
        
    }
    //Display elements
    public void display()
    {
        Node temp = head;
        while(temp!=null)
        {
            System.out.println(temp.data+" ");
            temp = temp.next;
        }
        System.out.println();
    }
}
public class Main
{
public static void main (String[] args)
{
    SinglyLinkedList list = new SinglyLinkedList();
    list.InsertAtBegin(10);
    list.InsertAtBegin(20);
    list.InsertAtBegin(30);
    list.InsertAtBegin(40);
    list.display();
    list.InsertAtEnd(50);
    list.InsertAtEnd(60);
    list.display();
    list.DeleteAtBegin();
    list.display();
    list.DeleteAtEnd();
    list.display();
    list.InsertAtAnyPosition(2,100);
    list.display();
}
}
