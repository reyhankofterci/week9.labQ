#include <stdio.h>
#include <stdlib.h>
#include <string.h>

struct student
{
 int number;
 char name_surname;
 int midterm_note;
 int final_note;
 struct student *next;
};

typedef struct student node;
node *head, *newnode, *previousnode, *successfulnode;


//1
void CreateStudentList()
{
    int n,k;
    printf("how many students are on the list");
    scanf("%d",&n);

    for(k=0; k<n; k++)
    {
        if(k==0)
        {
            newnode = (node *)malloc(sizeof(node));
            head=newnode;
        }
        else
        {
            newnode -> next = (node *) malloc(sizeof(node));
            newnode = newnode -> next;
        }
        printf("Student No: \n");
        scanf("%d",&newnode -> number);
        printf("Student Name Surname: \n");
        scanf("%s",&newnode -> name_surname);
        printf("Student Midterm Note: \n");
        scanf("%d",&newnode -> midterm_note);
        printf("Student Final Note: \n");
        scanf("%d",&newnode -> final_note);
    }
    newnode -> next = NULL;
}

//2
void ListStudents()
{
    double Note = 0;
    node *p;
    p = head;
    while(p!=NULL)
    {
        printf("\n \t ------------------- \n");
        printf("Student No: %d \t", p -> number);
        printf("Student Name Surname: %s \t", p -> name_surname);
        printf("Student Midterm Note: %d \t", p -> midterm_note);
        printf("Student Final Note: %d \t",p -> final_note);

        Note = p -> midterm_note*0.4 + p-> final_note*0.6;

        printf("Semester Not : %.3f \t", Note);
        printf("\n \t ------------------- \n");
    }
}


//3
void AddStudent()
{
    int RegistrationNo;
    node *p, *q;
    newnode = ( node *) malloc(sizeof(node));

    printf("Student No: ");
    scanf("%d",&newnode -> number);
    printf("Student Name Surname: ");
    scanf("%s",&newnode -> name_surname);
    printf("Student Midterm Note: ");
    scanf("%d",&newnode -> midterm_note);
    printf("Student Final Note: ");
    scanf("%d",&newnode -> final_note);

    printf(" Which one do you want to add before?");
    printf("\n Press 0 to add it to the end of the list");
    scanf("%d",&RegistrationNo);

    p = head;
    if(p -> number == RegistrationNo)
    {
        newnode -> next = p;
        head = newnode;
    }
    else
    {
        while(p -> next != NULL)
        {
            q=p;
            p=p -> next;
            if(p-> number ==RegistrationNo)
            break;
        }
        if(p->number == RegistrationNo)
        {
            q->next = newnode;
            newnode -> next = p;
        }
        else if(p-> next == NULL)
        {
            p -> next = newnode;
            newnode -> next = NULL;
        }
    }
}


//4
void DeleteStudent()
{
    int RegistrationNo;
    node *p, *q;

    printf("Enter the student number you want to delete");
    scanf("%d", &RegistrationNo);

    p = head;
    if(p->number == RegistrationNo)
    {
        head = p-> next;
        free(p);
    }
    else
    {
        while(p-> next !=NULL)
        {
            if(p->number == RegistrationNo)
                break;
            else
            {
                q=p;
                p=p -> next;
            }
        }
        if(p->number == RegistrationNo)
        {
            q -> next = p-> next;
            free(p);
        }
        else if(p-> next == NULL)
        {
            print("There is no student number to delete");

        }
    }
}


double CalculateSuccessGrade(int midterm_note, int final_note)
{
    return(0.4*midterm_note)+(0.6*final_note);
}


//5
void MostSuccessfulStudent()
{
    double successfulnote =0;

    node *p;
    p = head;
    MostSuccessfulStudent = head;

    while (p-> next !=NULL)
    {
        p=p-> next;
        if(CalculateSuccessGrade(p->midterm_note, p->final_note)>CalculateSuccessGrade(MostSuccessfulStudent->midterm_note, MostSuccessfulStudent->final_note))
        MostSuccessful = p;
    }
    printf("Most Successful Student: \n");
    printf("No: %d  -  Name Surname: %s  -  Note : %.2f \n",MostSuccessfulStudent->number, MostSuccessfulStudent -> name_surname, CalculateSuccessGrade(MostSuccessfulStudent->midterm_note, MostSuccessfulStudent-> final_note));

}




void ClassAverage()
{
    double NoteAverage =0;
    double sum =0;
    int counter =0;
    node *p;
    p= head;
    if (p==NULL)
    {
        printf("There are no records in the list");
    }
    else
    {
        do
        {
            sum += calculatenote(p->midterm_note,p->final_note);
            p=p->next;
            counter++;
        }
        while(p!= NULL);

        NoteAverage = sum/counter;
        printf(" class Average : %.2f \n",NoteAverage);
    }
}


int main (void)
{
    int choise = 0;
    printf("1-Create a List \n");
    printf("2-Add New Student \n");
    printf("3-Delete Student \n");
    printf("4-Hightest Note \n");
    printf("5-Class Average \n");

    while(1)
    {
        printf ("Choise(1-5)?");
        scanf("%d",&choise);

        switch(choise)
        {
        case 1 : CreateStudentList();
            break;

        case 2 : ListStudents();
            break;

        case 3 : AddStudent();
            break;

        case 4 : DeleteStudent();
            break;

        case 5 : MostSuccessfulStudent();
             break;

        case 6 : ClassAverage();
            break;

        }
    }

}
