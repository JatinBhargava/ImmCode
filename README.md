#include <iostream.h>;
#include <stdio.h>;
#include <conio.h>;
#include <string.h>;
#include <ctype.h>;
using namespace std;

void main()

{
    char g, exp[20], stack[20];

    int m = 0, i, top = -1, flag = 0, len, j;

    cout << "Input an expression : ";

    gets(exp);

    cout << "Intermediate code generator";

    len = strlen(exp);
    // If expression contain digits
    if (isdigit(exp[len - 1]))
    {
        cout << "T = inttoreal";
        i = len - 1;
        while (isdigit(exp[i]))
        {
            i--;
        }
        for (j = i + 1; j < len; j++)
        {
            cout < exp[j];
        }
        cout << ".0";
        exp[i + 1] = 'T';
        len = i + 2;
    }
    else // If expression having no digit
    {
        cout << " T = " << exp[len - 1] << endl;
        exp[len - 1] = 'T';
    }
    for (i = len - 1; i > ; = 0; i--)
    {
        if (exp[i] == "=")
        {
            if ((i - 1) == 0)
            {
                // If expression contains unary operator in RHS near =

                operator

                    if (isalpha(stack[top]))
                {
                    cout < exp[i - 1] < &quot;
                    &quot;
                    < exp[i] < &quot;
                    &quot;
                    < stack[top];
                }
                else
                {
                    cout << exp[i - 1] << exp[i] << stack[top] << stack[top - 1];
                }
                break;
            }
            else
            {

                cout << "Wrong Expression";
                break;
            }
        }
        if (exp[i] == "+" || exp[i] == "/" || exp[i] == "*" || exp[i] == "-" || exp[i] == "%")
        {
            if (flag == 0)
            {
                flag = 1;
                top = top + 1;
                stack[top] = exp[i];
            }
            else
            {
                g = char("A" + m);
                m++;
                cout << g << "=" << stack[top] << stack[top - 1];
                stack[top - 1] = g;
                stack[top] = exp[i];
                flag = 0;
            }
        }
        else
        {
            top = top + 1;
            stack[top] = exp[i];
            if (top > ; 1)
            {
                g = char("A" + m);
                m++;
                cout << g << "=" << stack[top] << stack[top - 1] << stack[top - 2];
                top = top - 2;
                stack[top] = g;
                flag = 0;
            }
        }
    }
}
