input:

#include <iostream>
#include <cmath>
using namespace std;

int main() {
    cout << "=== Command-Line Calculator ===" << endl;
    cout << "Operations: +  -  *  /  %  sqrt  pow  sin  cos  tan" << endl;

    while (true) {
        cout << "\nEnter operation (or type 'exit' to quit): ";
        string op;
        cin >> op;

        if (op == "exit") {
            cout << "Exiting calculator. Goodbye!" << endl;
            break;
        }

        double a, b;

        if (op == "+" || op == "-" || op == "*" || op == "/" || op == "%") {
            cout << "Enter two numbers: ";
            cin >> a >> b;

            if (op == "+") cout << "Result: " << a + b << endl;
            else if (op == "-") cout << "Result: " << a - b << endl;
            else if (op == "*") cout << "Result: " << a * b << endl;
            else if (op == "/") {
                if (b == 0)
                    cout << "Error: Division by zero!" << endl;
                else
                    cout << "Result: " << a / b << endl;
            }
            else if (op == "%") cout << "Result: " << fmod(a, b) << endl;
        }
        else if (op == "sqrt") {
            cout << "Enter number: ";
            cin >> a;
            if (a < 0)
                cout << "Error: Negative number!" << endl;
            else
                cout << "Result: " << sqrt(a) << endl;
        }
        else if (op == "pow") {
            cout << "Enter base and exponent: ";
            cin >> a >> b;
            cout << "Result: " << pow(a, b) << endl;
        }
        else if (op == "sin" || op == "cos" || op == "tan") {
            cout << "Enter angle in degrees: ";
            cin >> a;
            double rad = a * M_PI / 180.0;

            if (op == "sin") cout << "Result: " << sin(rad) << endl;
            else if (op == "cos") cout << "Result: " << cos(rad) << endl;
            else if (op == "tan") cout << "Result: " << tan(rad) << endl;
        }
        else {
            cout << "Invalid operation!" << endl;
        }
    }

    return 0;
}


output:

=== Command-Line Calculator ===
Operations: +  -  *  /  %  sqrt  pow  sin  cos  tan

Enter operation (or type 'exit' to quit): +
Enter two numbers: 12 8
Result: 20

Enter operation: sqrt
Enter number: 49
Result: 7

Enter operation: sin
Enter angle in degrees: 30
Result: 0.5

Enter operation: exit
Exiting calculator. Goodbye!
