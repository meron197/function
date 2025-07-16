# function
#include <iostream>
#include <string>
using namespace std;

float add(float a, float b);
float subtract(float a, float b);
float multiply(float a, float b);
float divide(float a, float b);
int modulusint(int a, int b); 

int main() {
    float num1,num2,result;
    char op;
    string proceed;

    do {
        cout << "Enter the first number: ";
        cin >> num1;
        cout << "Enter the second number: ";
        cin >> num2;
        cout << "Enter the operator (+, -, *, /, %): ";
        cin >> op;

        switch (op) {
            case '+':
                 result = add(num1, num2);
                break;
            case '-':
                 result = subtract(num1, num2);
                break;
            case '*':
                 result = multiply(num1,num2 );
                break;
            case '/':
                if (num2== 0) {
                    cout << "Division by zero is not allowed." << endl;
                    continue;
                }
                 result = divide(num1,num2);
                continue;
            case '%':
            if ((int)num2 == 0) {
                cout << "Cannot divide by zero" << endl;
                continue;
            }else
                result = (float)modulusint((int)num1, (int)num2);  
                 cout << "Result: " << result << endl;
            continue;
            default:
                cout << "Invalid operator." << endl;
                break;
        }

        cout << "the result is " <<result<< endl;
        cout << "Do you want to do another operation? (yes/no): ";
        cin >> proceed;

    } while (proceed == "yes");

    return 0;
}


float add(float a, float b) { return a + b; }
float subtract(float a, float b) { return a - b; }
float multiply(float a, float b) { return a * b; }
float divide(float a, float b) { return a / b; }
int modulusint(int a, int b) { return a % b; }


