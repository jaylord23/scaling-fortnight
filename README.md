/* + Write a program in C to calculate and print the Electricity bill of a given customer.
+ The customer ID., and Unit Consumed by the user should be inputted.
+ Print All Customer Data (Customer ID., Unit Consumed, Unit Charges, Surcharge, Customer Total Bill)*/

#include<stdio.h>

// function prototype declaration
    void info (int ID, int kWh);
    void Unit_charges (int kWh);
    void Surcharge ();
    void Total ();
    float charges, surcharge;

int main()
{

    int ID, kWh;

    printf("Input Customer ID:");
    scanf("%d",&ID);
    printf("Input the unit consumed by the customer:");
    scanf("%d",&kWh);

    printf("\n[ELECTRICITY BILL]\n\n");

    // function call
    info (ID, kWh);
    Unit_charges (kWh);
    Surcharge ();
    Total();
    return 0;
}
// First function : Determine the Charge Unit
    void info (int ID, int kWh)
    {
    printf("Customer ID#\t\t: %d\n", ID);
    printf("Unit consumed\t\t: %d\n", kWh);
    }

//Second Function : Calculate Unit Charges
    void Unit_charges (int kWh)
    {
    float  unit;
    if(kWh<199)
    unit= 1.50;
    else if(kWh>=250 && kWh<400)
    unit= 1.60;
    else if(kWh>=450 && kWh<600)
    unit= 1.85;
    else
    unit= 2.00;
    charges= kWh*unit;
    printf("Unit charges @P%.2f\t:P %.2f\n",unit,charges);
    }

//Third Function : Calculate Surcharge
    void Surcharge ()
    {
    int sch;
    if (charges > 400)
    surcharge= charges * 10 / 100;
    else (charges < 100);
    sch= 0;
    printf("Surcharge amount \t:P %.2f\n",surcharge,sch);
    }

// Fourth Function : Calculate Total Customer Bill
    void Total ()
   {
    float total;
    total= charges + surcharge ;
    printf("Total Customer Bill\t:P %.2f", total);
   }
