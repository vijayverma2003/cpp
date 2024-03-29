# C++

## Your first C++ program

```c++
#include <iostream>

int main()
{
    std::cout << "Hello World";
    return 0;
}
```

**int** stands for integer, means our main function is gonna return an integer.

**#include** is used for using CSL, that is C++ standard library. The standard library provides bunch of capabilties that we need when creating applications after **#include** we in angle brackets we write the file we want to include, in above program we included **iostream** which is short for _input output stream_, in this file we have capabilities for printing something on the screen or getting input from the user.

After that in the function we type **std** which is a bucket of features available to us and we can access those features by using double colons (_::_).

**cout** is one of the features that is short for character out. Using this object we can output one or more characters on the screen.
To use that we use double left angle brackets and type the text we want to display and terminate it with a semicolon (_;_). This line we wrote is called a **statement** because it tells the operating system what to do. Finally, we return the value **0** and terminate it with semicolon, and we return 0 to tell the operating system that our program is gonna terminate correctly. If we return any other other value that is positive or negative that means our program encountered an error.

For converting this c++ code to machine code, we click on the play button on the top right corner, or use shortcut.

**_Summary_** -

1. First, we include the iostream file which provides various features for printing and taking inputs on the screen.
2. Then we defined the main function that is entry level to program.

## The basics

**Variables**

In programming, we use variables to temporarily store data in the computer's memory. Technically, variable is an address to computer memory where value is stored and as value can be changed so it's called an variable.

For declaring variables firstly we write their type and then give variable a name and then initialize its value. We can always create a variable without initializing it, and when we print it we see a completely random value which is **garbage**.

```c++
int file_size = 10;
```

We can also declare two variables in one line, but that's not a good practice.

```c++
int file_size = 10, counter = 0;
```

**Constants**

For declaring variables that can't be changed we use **const** keyword.

```c++
const double pi = 3.14;
```

**Notations**

> Snake Case - file_size

> Camel Case - fileSize

> Pascal Case - FileSize

> Hungarian Notation - iFileSize

In Hungarian Notation the name of variable starts with the first letter of it's type.

**Mathematical Experssions**

Like most of programming language we have add, subtract, multiply, division, modulas, increment and decrement operator but in C++ we have division on the basis of its types. For example, we have two integers but their result of division is a double it will still return a integer, to get a double as a result for one of the variable we have to convert its type to double.

```c++
double x = 10;
int y = 3;
double z = x/y; // returns 3.33333
```

Increment and decrement operator can be used as prefix and postfix. With prefix, first their value will be changed then it will be used and in postfix, first their value will be used and then it will be changed.

```c++
int x = 10;
int y = ++x; // x = 11, y = 11
int z = x++; // x = 11, z = 10
```

**Writing output to the console**

For writing something in console, we use **std::cout** which is called **Standard Output Stream**, Stream stands for sequence of characters and Standard Output is our console or terminal window.

The **<<** double brackets are called **Steam Insertion Operator**. It's an operator for inserting something to our output stream.

_To print x = 10 in terminal we write_

```c++
int x = 10;
std::cout << "x = " << x;
```

Now, if we want to print one more variable, it will end up in same line, so we have to end this stream with **std::endl**, which is short for endline.

```c++
int x = 10;
int y = 5;
std::cout << "x = " << x << std::endl;
std::cout << "y = " << y

// or

std::cout << "x = " << x << std::endl
          << "y = " << y;
```

Now, we have repetition everywhere, that is **std::**, to remove that, we use a namespace, that makes std available everywhere in that file.

```c++
#include <iostream>

using namespace std;

int main() {
    int x = 10;
    int y = 5;
    cout << "x = " << x << endl
         << "y = " << y;
}
```

**Reading inputs from the console**

For reading inputs from the console, we use **cin** which is chain extraction operator followed by two right **>>** angle brackets.

```c++
    cout << "Enter two values x and y: ";

    double x;
    double y;

    cin >> x;
    cin >> y;

    // Short:  cin >> x >> y;

    cout << x + y;
```

**Working with the standard library**

_Click on [cmath](https://cplusplus.com/reference/cmath/) to view the documentation._

```c++
#include <iostream>
#include <cmath>

using namespace std;

int main() {
    cout << "Enter radius of circle: ";

    double radius;

    cin >> radius;

    double area = 3.14 * pow(radius, 2);

    cout << area;
    /*
    */
}
```

_If you are not able to take inputs in VS Code terminal, then go to **Code > Prefrences > Settings** and search for **Code-runner : Run in terminal** and check that._

**Comments**

For declaring comments, we use **//** or **/\* \*/** to create a block comment.

## Fundamental data types

We have seen that when we declaring a variable we have to specify it's type and this type can not change through the lifetime of our program, that's why **C++ is a statically type language**.

**short**

Takes **2B** of memory and ranges between -32,768 to 32,768.

**int**

Takes **4B** of memory on most systems and ranges between -2B to 2B.

**long**

For storing large numbers and its range and memory is same as int.

```c++
 long file_size = 90000L;
```

**long long**

Takes 8B of memory for storing very large numbers but it's not used oftenly.

**float**

Range: -3.4 x e<sup>38</sup> to 3.4 x e<sup>38</sup> Memory: 4B

```c++
 float interestRate = 3.67F;
```

We have to type **F** at the end, because otherwise compiler will take it as a double and store it in float, and this can potentially result in data loss.

**double**

Range: -1.7 x e<sup>308</sup> to 1.7 x e<sup>308</sup> Memory: 8B

**long double**

Range: -3.4 x e<sup>932</sup> to 1.7 x e<sup>4832</sup> Memory: 8B

**bool**

For storing, true and false values take **1B** of memory.

**char**

For storing single character takes **1B** of memory.

```c++
char letter = 'a';
```

_We can also use **auto** keyword to auto detect it's type, but for floats and longs we have to write their postfix, otherwise they will be stored as double or int._

**Brace Initializer**

In C++20, We have new method for initilizing variables. Normally, we can assign an int to a floating number but it will compile and result will be shown as an int. But with brace initializers, it shows an error, and if we don't supply a value, it will initialize it to 0 instead of garbage.

```c++
int number {};
cout << number;

// prints 0

int number {1.2};
cout << number;

// error

int number {1};
cout << number;

// prints 1
```

**Number Systems**

In our daily like we use decimals called **base10** system stores from 0-9.

Computers uses **base2** system called Binary that only store 0 and 1.

```c++
int number = 0b11111111; // 255
```

**base16** system called Hexadecimal stores 0-9 and A-F.

```c++
int number = 0xff; // 255
```

_There is a keyword **unsigned** which can be used to store positive values in an int, but we should not use that, because if we accidently decrement that number or change its value to negative, it will return a very huge number._

If we, store an int as a short, it will be narrowed down to a short number to fit in the memory but we can store a short in int as same value.

```c++
int number = 1000000;
short another = number;
cout << another;

// returns 16960
```

**Generate Random Numbers**

```c++
#include <iostream>
#include <cstdlib>
#include <ctime>

using namespace std;

int main()
{
    srand(time(nullptr));
    int number = rand() % 10;

    cout << number;

    return 0;
}
```

**srand** is used to seed the rand value, if we pass the same value, it will return the same number again and again, that's why we use **time** function that returns the time in seconds from JAN 1, 1970.

**[(max_value - min_value + 1) + min_value]** is the formula to generate a random number between two numbers.

**Formatting Outputs**

The printed string on the terminal are right next to each other but what if we want to organize into columns, that's when we use one of the **stream manipulators** in C++. A steam manipulator is a function that is used to modify or manipulate the stream.

One of the function is **setw** which is used to reserve the number of character for the data that comes after and one is **left**, that is used to align everything that comes after to left, it's called a sticky manipulator because once we applied its gonna be in effect until we change it. In contrast, **setw** is not sticky, because it only applies to what comes after. Similary we have **right**, but we don't need to apply it because stream is already right aligned.

```c++
#include <iostream>
#include <iomanip>

using namespace std;

int main()
{
    cout << left;
    cout << setw(10) << "Spring" << setw(10) << "Nice" << endl
         << setw(10) << "Summer" << setw(10) << "Hot";

    return 0;
}

// Stream    Nice
// Summer    Hot
```

**Data type size and limits**

Other manipulators are fixed and setprecision. **fixed** manipulator is used to print the number using fixed point notation and **subprecision** is used to set the precision of a double. These both manipulators are sticky.

```c++
cout << fixed << setprecision(5) << 12.34567;
```

**sizeof** function is used to get size of a data type in your machine, most of the systems have same size, but it may differ in some machines.

```c++
int number = numeric_limits<int>::max();
number++;
cout << number;

// -2147483648
```

The concept above is called Overflowing, but the value for the data is too large to store in its type, it overflows and stored as a minimum value in the variable.

The other concept is called underflowing, but instead of smaller value, if the value is extremely smaller then the maximum value is stored in the variable.

**Working with booleans**

When we print a bool on terminal, then it return 0 for false, or 1 for true. To get the value true/false printed in terminal, we use **boolalpha** stream manipulator and we can use **noboolalpha** for the opposite.

**Working with Characters and Strings**

We use **char** for storing single character and **string** for storing sequence of characters.

```c++
char ch = 'a';
cout << ch; // a
cout << +ch; // 97
```

_We can also declare the char variable with their numeric representation and when printed they will print their respective character_

```c++
 string street;
    cout << "Street: ";
    getline(cin, street);

    string city;
    cout << "City: ";
    getline(cin, city);

    string state;
    cout << "State: ";
    getline(cin, state);

    string zipCode;
    cout << "Zip Code: ";
    getline(cin, zipCode);

    cout << street << endl
         << city << ", " << state << ", " << zipCode;
```

We use **getline** manipulator to get a string input with spaces between words.

**Arrays**

We use arrays, to store a collection of elements like numbers, dates, strings and so on.

```c++
int numbers[5]; // numbers array is initialized with size of 5 with value 0;

int numbers[] = {10, 20}; // numbers have length of 2

cout << numbers; // returns the address in memory as hexadecimal

cout << numbers[2]; // returns garbage

cout << numbers[1] // returns 20
```

**Type Conversion**

```c++
int x = 1;
double y = 2.2;
double z = x + y;

// 3.2, under the hood, the compiler changes the type of x to double, and this will not result in data loss, because we are casting
// a 4B data to 8B.

int x = 1;
double y = 2.2;
int z = x + y; // Warning, data loss may or may not happen

// C style casting
int z = x + (int)y;

// C++ casting
int z = x + static_cast<int>(y);

// With this, if the conversion can't be done the compiler will tell us, and is safer than C style casting.
```

## Decision Making

**Comparison Operators**

**>, >=, <, <=, ==, !=** are the comparison operators which are used to compare two values, also we can compare two different types like int and double, when compiled the low precision type will be converted to high precision type, in this case, int will be converted to double.

```c++
int x = 10;
double y = 5.0;

// Boolean expression, an expression is an statement which returns a value
bool result = x != y;

cout << boolaplha << result
```

**Logical Operators**

We use logical operators (**&&, ||, and !**) to combine two or more comparison operators.

**Order of logical operators**

> || => && => ! => ()

**if Statements**

```c++
...

int main()
{
    int sales = 16000;
    double commission;

    if (sales <= 10000)
        commission = .1;
    else if (sales > 10000 && sales <= 15000)
        commission = .15;
    else
        commission = .2;

    cout << commission;

    return 0;
}

...
```

**Conditional Operator**

```c++
int sales = 11000;
double commission;

commission = (sales > 10000) ? .1 : .05;

```

**Switch Case**

We can use switch case to only check the value, we can't compare as we do in if else statements.

```c++
...
    cout << "1 - Create Account" << endl
         << "2 - Change Password" << endl
         << "3 - Quit" << endl
         << "Choose an option: ";

    int input;

    cin >> input;

    switch (input)
    {
    case 1:
        cout << 'You selected 1';
        break;
    case 2:
        cout << 'You selected 2';
        break;
    default:
        cout << 'Goodbye!';
    }

...
```

## Loops

**for loop**

```c++
for(int i = 0; i < 5; i++)
    cout << i << endl;
```

**Range based for loops**

```c++
int numbers[] = {1, 2, 3, 4, 5};

for(number: numbers)
    cout << number;
```

_It can be also used for string._

To get the length of an array, we use **sizeof(array_name) / sizeof(type_of_array)**

**while loops**

```c++
int main()
{
    int secretNumber = 7;

    int input;

    while (input != secretNumber)
    {
        cout << "Guess: ";
        cin >> input;
    }

    return 0;
}
```

**do while loop**

Difference between **while** loop and **do while** loop is that, do while is always executed atleast once because it's condition lies after the **do** block.

```c++
do {
    ...your code
} while (condition);
```

**break and continue**

**continue** is used for continuing the loop and code after that will not be excuted. **break** keyword is used to break out of the loop.

## Functions

```c++
[type_of_return_value] [name_of_function](...params) {
    ...
}

string fullName(string firstName, string lastName) {
    return firstName + ' ' + lastName;
}
```

**Default Parameters**

We can assign a default value to parameter like we declare a variable but after that parameter every parameter need to be defined before that or defined with a default value.

**Overloading Functions**

When we want to change parameters of function, but not the name of function then we can define another function with same name and call them according to their parameters.

When using overloading functions, we need to remember a concept called **Signature**. When overloading functions we should have a unique signature.

> Signature = Name of funtion + (number and types of parameters)

If we have same function with same number and types of parameters then we will get an error.

**Passing arguments by value or reference**

In C++, we can pass variables as the arguments as like in every programming language. So when a function is called, the value is copied to that function and then function does the work. But what if we need to pass the high amount of data, the function will copy that data, that will take so much time. That's when we pass arguments by reference.

```c++
// In this case, double is only 8bits so it is very fast operation.
void price(double price) {
    price *= 2;
}

// We need to use the '&' after the type of parameter to pass its value by reference.

void greet(string& name) {
    cout << name;
}

// But, what if we accidently change the value in function of that argument that is passed by reference
// that's when we declare the variable as constant

void greet(const string& name) {
    cout << name;
}
```

**Avoid global variables as much as possible**

**Declaring Functions**

What if we want to declare a function after the main function, we will get an error but what if we want to origranize our code better, that's when we use **function declaration or function prototype**.

```c++
// Function declaration or function prototype
void greet();


void main {
    ...
}


// Function definition
void greet() {
    ...
}
```

**Organising functions in files**

For separting function into files, we have to create two files, one is header file that has function declarations and the other is the file where we define our functions. The header file have extension **h++**.

Now, there is a tiny problem, what if we include that function in many different files, then this will be imported again to prevent that we define a variable on the top of file.

```c++
#ifndef UTILS_GREET
#define UTILS_GREET

#include <string>

void greet(std::string name);

#endif
```

Now, when our code is compliled, this will be compiled only once.

**Using Namespaces**

Now, we can use function made by other people, but what if they have same function as ours and it clashes, that's when we use namespaces. A namespace is like a bucket where we put our functions inside, and with this prevent name conflicts.

To create a namespace, we use **namespace** keyword.

```c++
namespace messaging {
    ...hpp content in hpp file
    and cpp content in cpp file
}
```

We can use these namespaces as we used before for **std**.

```c++
using namespace std;
using namespace messaging;

// If the name still clashes for the methods of namespaces, we can get a single function from namespace or multiple too.

using messaging::greet;
using std::cout, std::cin;
```

## Arrays

Arrays are used to store number of elements in memory.

```c++
int first[5]; // Array of size 5 is initialized
first[0] = 10;
first[1] = 20;

// We can also use brace initialization to initialize the array.

int second[] = { 1, 2 };
```

**Determining the size of arrays**

```c++
#include <iostream>

using namespace std;

int main() {
    int numbers[] = {1, 2};

    cout << sizeof(numbers) / sizeof(int);

    cout << size(numbers); // 2

    return 0;
}
```

**Copying Arrays**

In C++, We can't copy array by assigning the first array to other. To do so, we have to loop over it, and copy each value.

```c++
...

int first[] = {1, 2, 3, 4, 5};
int second[size(first)];

for(int i = 0; i < size(first); i++)
    second[i] = first[i];

for(int number: second)
    cout << number;

...
```

**Comparing Arrays**

We can't compare arrays by their variables, because arrays are compared on basis of their memory address.So, we have to 
iterate over the array and then compare its values.


```c++
int first[] = {1, 2, 3, 4, 5};
int second[] = {1, 2, 3, 4, 5};

bool areEqual = true;

for(int i = 0; i < size(first); i++) {
    if(first[i] != second[i]) {
        areEqual = false;
        break;
    }
}

cout << boolalpha << areEqual;
```

**Passing Arrays to Functions**

When we pass an array to a function, the array type is converted to a pointer. In the following example the int array
will be converted to an int pointer "int*", so, we can't use range based for loop on that instead we have to use a 
traditional for loop. Also, as int array is converted to int* we always have to pass the size of array to function too.


```c++
#include <iostream>

using namespace std;

void printNumbers(int numbers[], int size) {
    for(int i = 0; i < size; i++)
        cout << numbers[i] << endl;
}

void main() {
    int numbers[] = {1, 2, 3, 4, 5};
    printNumbers(numbers, size(numbers));
    
    return 0;
}
```

**Understand size_t**

**size_t** is one of the function provided in iostream, that is type of return values of size and sizeof.
size_t is equivalent to unsigned long long type for 64 bit systems, and unsigned int for 32 bit systems.

So, basically, this is a data type for representing the sizes and this type is guaranteed to be large enough to contain
the size of largest type that system can handle.

```c++
cout << numeric_limits<size_t>::min() << endl; // 0
cout << numeric_limits<size_t>::max() << endl; // 18446744073709551615
```

**Unpacking Arrays**

In C++, it is called **structured binding**.
In JavaScript, it is called **destructuring**.
In python it is called **unpacking**.

```c++
int values[3] = {1, 2, 3};

auto [x, y, z] = values;
```

**Searching Arrays**

Linear Search Algorithms

```c++
int linearSearch(int target, int numbers[], size_t size) {
    for(int i = 0; i < size; i++) {
        if(target == numbers[i]) return i;
    }

    return -1;
}
```

**Sorting Arrays using Bubble Sort**

```c++
void swap(int numbers[], int a, int b) {
    int temp = numbers[a];
    numbers[a] = numbers[b];
    numbers[b] = temp;
}

void bubbleSort(int numbers[], int size) {
    for(int pass = 0; pass < size; pass++) {
        for (int i = 1; i < size; i++)
            if (numbers[i] < numbers[i - 1])
                swap(numbers, i, i - 1);
    }
}
```

**Multi Dimensional Arrays**

```c++
const int rows = 2;
const int columns = 3;

void printMatrix(int numbers[rows][columns]) {
    for(int i = 0; i < rows; i++)
        for(int j = 0; j < columns; j++)
            cout << numbers[i][j] << endl;
}

int main() {
    int numbers[rows][columns] = {
            {11, 12, 13},
            {21, 22, 23}
    };

    printMatrix(numbers);

    return 0;
}
```

## Pointers

A pointer is a special variable that hold the address of another variable in memory.

For example, we have a variable which holds the value number 10. As you know, a variable is just a label for a memory
address. Now we can declare other variable called ptr that holds the address of number.

There are few reasons for using pointers.

> Efficiently passing large data

> Dynamic memory allocation

> Enabling Polymorphism

To get the address of an variable we prefix the variable with **&** and this is called **address-of operator**.

```c++
int number = 10;
cout << &number; // 0x16fa2f448
```

To initialize a pointer we postfix a variable by *.

```c++
int number = 10;

int* ptr = &number;
```

If we don't initialize the pointer then like other uninitialized variables, it's gonna hold **garbage**.
The problem with this uninitialized pointer is that we might access the part of memory we are not supposed to and in that
case the operating system gonna terminate our program and say **memory access violation**.

If we don't know,for what variable it's gonna be initialized, we can initialize it to null pointer with keyword **nullptr**.
A **nullptr** is a pointer that doesn't point to anything. In old C++, it was initialized with **NULL** or **0** but now 
in modern C++ we have **nullptr**. 

With **nullptr**, we can also check to see if ptr is initialized using if block.

```c++
if(ptr != nullptr) {
    ...
}
```

We have another **Indirection or de-referencing operator**, with that we can access the data for the memory location that
pointer is holding.

```c++
int number = 10;

// The & is the address-of operator
int* ptr = &number;

cout << *ptr; // 10

// Indirection or de-referencing operator
*ptr = 20;

cout << number; // 20
```

Note that, pointers can also be initialized like **int \*ptr = &number;**, but we should not follow this approach, because
it can confusing with **Indirection or de-referencing operator**.

**Constant Pointers**

There are three scenarios, when using constant pointers.

1. Data is constant.
2. Pointer is constant.
3. Data and Pointer both are constant.

```c++
// Data is constant
// We have to set the same type for the pointer, and with that pointer can't change value of x using InDirection operator.
// But we can still change the value of ptr to store a different address.
const int x = 10;
const int* ptr = &x;

// Pointer is constant
// We have to write const after the asterisk to declare a constant pointer.
int x = 10;
int* const ptr = &x;

// When both are constant
const int x = 10;
const int* const ptr = &x;

// Now, neither ptr can be changed nor the variable it is holding the address of. 
```

**Passing pointers to functions**

Previously, we passed the props in a function as arguments using reference operator which is modern way, but we can also
pass data to function using pointers.


```c++
void increasePrice(double& price) {...} // Reference operator

// Passing props with pointers

void increasePrice(double* price) {
    *price *= 1.2;
}

void main() {
    double price = 100;
    increasePrice(&price);
    
    cout << price; // 120
    
    return 0;
}
```


**Relationship between pointers and arrays**

Now, as we know that when we print any array on console, we see its memory address, which is actually a pointer.

```c++
int numbers[] = {10, 20, 30};
int* ptr = numbers;

cout << *ptr; // 10, the address of array holds the first value of the array

// With that we can also access other elements

cout << *ptr[1]; // 20
```

Also, when we pass arrays to functions, their address is passed that's why we can't iterate or use size function over
them. That's why we always pass the size as arguments to the function because we can access the values using a pointer
as shown in above example.

**Pointer Arithmetic**

For example we have an int array, and then we create a pointer variable. With that pointer, we can add or subtract intergers
with it.

If we increment the pointer by 1, it will be incremented by the size of its data type, for example if the int is stored
at 100 in memory. Then in memory it will store the first element from 100-103 as int takes 4 bytes of memory.

```c++
int numbers[] = {1, 2, 3, 4};
int* ptr = numbers;

cout << ptr; // 1

ptr++;

cout << ptr; // 2
```

Similarly, we can use subtract, but we can't use any other operators.

**Comparing Pointers**

We can compare pointers address, by using == or != operators also > , < in arrays.

```c++
// Print numbers from last element to first, by using pointers.

int main() {
    int numbers[] = {10, 20, 30};

    int* ptr = &numbers[size(numbers) - 1];

    while(ptr >= numbers) {
        cout << *ptr << endl;
        ptr--;
    }

    return 0;
}
```

**Dynamic Memory Allocation**

Now, we if we create an array, we have to supply its limit, but what if user passes more than that, or so less that our
memory is wasted that's when we use pointers for dynamic memory allocation. Now, for that first we create an array with
space of 10. Then during our program execution or at runtime, if we need more space, we can allocate it on demand, this 
is dynamic memory allocation. Now to allocate memory dynamically, we use different syntax.

```c++
// Stored in memory called Stack
int numbers[] = {1, 2, 3};

// Stored in memory called Heap (Free Store)
int* numbers = new int[10];
```

The good thing about variables stored in **stack memory** is that, when a function finishes execution, the memory is automatically
released when out of scope, and we can use that space again for another functions.

Now, In contrast, when we declare a variable on the heap using new operator, we are responsible for clean up and that
means if we don't do our job properly the memory allocated for the variables will never get released and our program is
gonna end up consuming more and more memory and eventually its gonna crash. We say our program is having a **memory leak**
means constantly consuming more and more memory.

So, once we are finished with this variable we should always deallocate memory using the **delete operator**.

```c++
int* numbers = new int[10];
int* number = new int;

delete number;
delete[] numbers;

// Not mandatory, It's a good practice to always reset our variables

numbers = nullptr;
number = nullptr;
```

**Dynamically Resizing an Array** 

```c++
#include <iostream>

using namespace std;


int main() {
    int capacity = 5;
    int* numbers = new int[capacity];
    int entries = 0;


    while(true) {
        cout << "Number: ";
        cin >> numbers[entries];

        if(cin.fail()) break;
        entries++;

        if(entries == capacity) {
            // Create a temp array twice the size
            capacity *= 2;
            int* temp = new int[capacity];

            // Copy all the elements to new array
            for(int i = 0; i < entries; i++)
                temp[i] = numbers[i];

            // Have "numbers" pointer pointing to the new array
            delete[] numbers;
            numbers = temp;
        }
    }

    for(int i = 0; i < entries; i++)
        cout << numbers[i] << endl;


    delete[] numbers;

    return 0;
}
```

But, we have to never implement this our own, because it is already built in **C++ standard library** with class called
**Vector**.

**Smart Pointers**

Now, in real world, we have 100's or 1000's of functions where we use pointer variables to store in a heap but what if we
forget to free up the memory allocated to them, this will eventually result in memory means constantly increase in memory.
It seems easy to delete the pointer's memory, but in real world, with many function we can get confused where and when 
we have to delete a pointer. That's when we use Smart Pointers.

There are two types of smart pointers which are Unique and Shared pointers.

**Working with Unique Pointers**

A unique pointer is kind of pointer that holds the piece of memory it points to, so we can't have another unique pointer
pointing to the same variable for that we use shared pointers.

```c++
#include <iostream>
#include <memory>

using namespace std;


int main() {
    unique_ptr<int> x(new int);
    auto y = make_unique<int>();
    auto numbers = make_unique<int[]>(5);

    return 0;
}
```

**unique_ptr** is a generic class, so we pass the type in angle brackets and it creates an instance **x** pointing to the
pointer created using **new int**.

Now, this class have several methods so it automatically deletes the allocated memory when execution is finished.

We can also simplify it by using a generic function called **make_unique** and set the type auto to prevent the code from
being verbose.

_We can change the value of variables as same like other pointers, but we can't perform arithmetic operations on that._

**Using Shared Pointers**

Most of the times **unique pointers** are used, but we can use **shared pointers** where two pointers point to same 
memory location.

```c++
auto x = make_shared<int>();
*x = 10;

shared_ptr<int> y(x);

cout << y; // 10
```

## Strings

**C Strings**

To create a string using C string method, we declare a char array and use a special character **\0** to represent the
end of the array that is called **Null Terminator**.

Another way to initialize a string variable is String Literal.We wrap the string with double quotes to initialize a string
literal. Internally, it is stored as a char[] same as above example and that special character is added automatically.

```c++
// Using char []
char name[6] = {'V', 'i', 'j', 'a', 'y', '\0'};

// Using string literal

char name[6] = "Vijay";
```

Now we can always get the value of any index of string using bracket notation, and change its value.

```c++
char name[6] = "Vijay";

name[0] = 'v'; // Character Literal wrapped in single quotes.
```

_Literal is a fancy name in computer science for a value._

Now, we have a bunch of functions to work with **cstring** and for them we have to include **cstring** file but its already
included in iostream by default so we don't need to explicitly include that file. Most of the functions are used because
we can't compare two arrays or copy arrays like integers or something.

Also, if we are copying a variable to any other variable, we have allocate a large space so that it doesn't occupy the 
memory that is not needed.

```c++
    char name[50] = "Vijay";
    char lastName[] = "Verma";

    // To calculate the length of string
    cout << ::strlen(name) << endl; // 5

    // To concatenate two strings, and the first argument is changed to concatenated string.
    ::strcat(name, lastName); // name => VijayVerma

    // To copy a string, the first argument value is changed to the second argument's value.
    ::strcpy(name, lastName); // name => Verma

    // Comparing strings
    if(::strcmp(name, lastName) < 0) cout << "name alphabetically comes before lastName" << endl;
    else if(::strcmp(name, lastName) > 0) cout << "name alphabetically comes after lastName" << endl;
    else cout << "Equal" << endl; // Means it returns 0
```

**C++ Strings**

To declare a string variable we use string type implemented as a class in C++ Standard Library. Internally it uses a char[]
because in C++ we don't have a string type in C++. Now, instances of the string class, we call them string objects. Now, 
all these objects have different function that we can access using **.** operator.


```c++
    string name = "Vijay";

    name[0] = 'v';

    // Getting length of string
    cout << name.length();

    // Concatenating strings
    name  += "Verma";
    cout << name << endl; // Vijay Verma

    // Copying strings
    string another = name;

    // Comparing strings
    if(name == another) cout << "Same";

    // Checking if our string starts with a char or a string
    cout << name.starts_with('v');

    // Similarly, we have ends_with and empty to check if string is empty
    cout << name.empty();

    // front() method returns the first character of string similarly we have back().
    cout << name.front();
```

**Modifying Strings**

```c++
    string name = "Vijay";

    // We can use append method to add another string at the end of string.
    // Now, the append method like many other function is overloaded, so we have several different versions of this function.

    name.append(" Verma");
    cout << name << endl;
    // Vijay Verma

    // We have insert method to insert a string at a particular position.

    name.insert(0, "I am ");
    cout << name << endl;
    // I am Vijay Verma

    // erase method is used for erasing characters in a string starting from index and erases n characters.

    name.erase(0, 2);
    cout << name << endl;
    // am Vijay Verma

    // clear method to set the string to an empty string.

    name.clear();
    cout << name << endl;
    // ""

    // We can use replace method to replace some characters of a string.
    
    name = "Vijay";
    name.replace(0, 2, "VI");
    cout << name << endl;
    // VIjay
```

**Searching Strings**

**find** method takes the string as parameters and returns the position of that in the string.

```c++
string name = "Vijay Verma";
name.find('a'); // 3
```

We can optionally provide the second argument for start position to search for the string or character.

```c++
string name = "Vijay Verma";
name.find('a', 5); // 10
```

If we search for 'A' in above example, we will get a very large number, because it's return type is size_t that's why
it can't return a negative number but we can compare this value with -1. 

Now, we have similar method called **rfind**, but it searches start from the end of the string.


```c++
string name = "Vijay Verma";
name.rfind('a'); // 10
```

**find_first_of** is used to find occurrence of any character of string.

```c++
string name = "Vijay";
name.find_first_of(",.;"); // returns -1 but as the largest number of type size_t
```

Similarly, like **rfind** we have **find_last_of** to search from last in a string.

Also we have **find_first_not_of** and **find_last_not_of** which return the position that is not any of charters passed
as arguments.

**Extracting Substrings**

**substr(start_position, number_of_characters_to_extract)** function is used to extract a sub string from a string, it 
also takes two arguments and if we don't pass any arguments it returns the copy of a string.

```c++
    // Function to extract the first and last name from a name.
    
    string name = "Vijay Verma";

    auto index = name.rfind(' ');

    string firstName = name.substr(0, index);
    string lastName = name.substr(index + 1);

    cout << firstName << endl;
    cout << lastName << endl;
```

**Working with characters**

**islower** function is used to check if a given character is lower case or not.

```c++
string name = "Vijay Verma";
cout << islower(name[0]); // 0
```

> **isupper** function is used to check if a given character is upper case or not.

> **isalpha** function is used to check if a given character is an alphabet or not.

> **isdigit** function is used to check if a given character is a digit or not.

> **isspace** function is used to check if a given character is space or not.

> **toupper** is used to convert to upper case and returns the number that represents the upper case of any character.

```c++
cout << toupper('a'); // 65 for 'A'

// C style casting
cout << (char) toupper('a'); // 'A'
```

Similarly, we have **tolower**.


**String_Numeric Conversion Functions**

_The functions for converting strings to other type starts with s then to and then the first letter of type to convert into._

```c++
double price = stod("19.99"); // 19.99
double price = stod("19.x99"); // 19
double price = stod("x19.99"); // Exception
```

**to_string** is a overload function to convert many types to string type.

```c++
string str = to_string(19) // 19
string str = to_string(19.9) // 19.900000
```

If we want to have more control over how these numbers are converted, we use **streams**.


**Escape Sequences**

Escape sequences are used to escape some special characters.

```c++
string str = "C:\\my\\"; // C:\my\

string hello = "\"Hello World\""; // "Hello World"

char ch = '\''; // '
```

We use **\n** for new line and we can use **\t** for adding a tab.

**Raw Strings**

Escape sequences can be messier sometimes, that's when we use raw strings.

```c++
string str = R"("C:\Localdisk C\my folder\")"
```

# Classes

## What is Object Oriented Programming?

We have different ways to write software which is called **Programming Paradigm**. Some of them are Procedural, Functional, 
Object Oriented, Event Driven and many many more.

Object Oriented Programming is a paradigm where objects are the main building block for a software.

An object is a software entity that has attributes (properties) and functions (methods).

A class is a blueprint or recipe for creating objects.

Structures and more about data and classes are about data and behavior. So, a class combines data and functions that operates 
on data together. This is one of the main principal of OOP that is Encapsulation.

**Encapsulation means combining the data and functions that operate on the data into one unit.**


## Defining a Class



*Header File*
```c++
#ifndef C___RECTANGLE_H
#define C___RECTANGLE_H

// width and height are called Attributes, Member Variables, Fields, and Properties.
// getArea and draw are called member functions or methods.
class Rectangle {
    int width;
    int height;
    void draw();
    int getArea();
};


#endif //C___RECTANGLE_H
```

*Source File*
```c++
#include "Rectangle.h"
#include <iostream>

using namespace std;

void Rectangle::draw() {
    cout << "Drawing a rectangle..." << endl;
    cout << "Dimensions: " << width << ", " << height << endl;
}

int Rectangle::getArea() {
    return width * height;
}
```

The reason we have create a header file is because when we make any changes in header file every file related to it is 
recompiled whereas if we make changes in source files then only source files will be recompiled. This is the reason we have
to separate the implementation of a class from its interface.

Unlike structures all the the properties and methods of a class are private, to make them we have to type private: before
initializing them.

```c++
class Rectangle {
public:
    int width;
    int height;
    void draw();
    int getArea();
};
```

```c++
    Rectangle rectangle;
    rectangle.width = 10;
    rectangle.height = 20;

    cout << rectangle.getArea();
 ```

## Access Modifiers

When objects store bad data then we say they go in a invalid state.

**Data Hiding is also a principal of OOP, which says that a class should hide its internal data from the outside code and 
provide functions for accessing the data. This is when we use access modifiers.

**public, private and protected** are some of access modifiers we use to apply data hiding.

## Getters and Setters

```c++
// Header File
class Rectangle {
public:
    void draw();
    int getArea();
    // Getters or Accessors    
    int getWidth();
    // Setters or Mutators
    void setWidth(int width);
private:
    int width;
    int height;
};

int Rectangle::getWidth() {
    return width;
}

// Source File
void Rectangle::setWidth(int width) {
    if(width < 0)
        throw invalid_argument("width");
    this->width = width;
}
```

## Constructors

A constructor is a special function inside a class that is used to initialize variables.

```c++
// Header
public:
    Rectangle(int width, int height);

// Source
Rectangle::Rectangle(int width, int height) {
    setWidth(width);
    setHeight(height);
}

// Modern Way
Rectangle rectangle {10, 20};
// or
Rectangle rectangle(10, 20);
```

## Member Initializer List

```c++
Rectangle::Rectangle(int width, int height) : width{width}, height{height} {}
```

The above method to initialize variables is more efficient and the compiler initialize these variables in one go.
The first is width attribute and the width in curly braces is width parameter. If we do it other way, the complier will
create a member initializer list first and then initialize the variables but we can use this only for simple initializations.

We can initialize variables with both methods at same time.


## Default Constructor

Now, we can't create a rectangle without passing arguments for width and height parameters and to do so we have to create 
a **default constructor**. A default constructor is a constructor without any parameters.

```c++
class Rectangle {
public:
    Rectangle() = default;
    Rectangle(int width, int height);
```

If we don't create any constructor, C++ compiler automatically creates a default constructor but the moment we create a
constructor, it stops creating default constructor.

## Using the explicit keyword

If we create a class with a constructor that takes only one argument, then its called a **Converting Constructor**.

So, when we create an instance of that class, and pass it to a function we can also pass the argument for that constructor too.
and when the function will be executed it will create the instance of that class and then do its job. and to prevent that from
happening we use explicit keyword before the constructor initialization in header file.

```c++
class Person {
public:
    Person(int age);
    
private:
    int age;
};


// main.cpp

void showPerson(Person person) {...}

Person person {10};
showPerson(person);
// or
showPerson(10); // Conversion happens here.

// header file
public:
    explicit Person(int age);
`
```

## Constructor Delegation

We can define more constructors with more parameters but we don't want to repeat the same code for initializing the previous 
variables that is where **constructor delegation** comes to the picture. With this technique, we can have one constructor 
delegate the initialize of some variables to previous constructor.

```c++
Rectangle::Rectangle(int width, int height) {
    setWidth(width);
    setHeight(height);
}

Rectangle::Rectangle(int width, int height, const string &color) : Rectangle(width, height) // Constructor Delegation
{
    this->color = color;
}
```

## The copy constructor

When we create an instance, we can easily copy the first instance to a variable because under the hood the C++ Compiler 
generates a copy constructor that copies all the members of the object to the second object. But there are times, we want 
to change the logic of copying an object that's when we can create our own copy constructor.


```c++
...
public:
    Rectangle() = default;
    Rectangle(const Rectangle& source);
...


Rectangle::Rectangle(const Rectangle &source) {
    cout << "Copying Rectangle";
    this->width = source.width;
    this->height = source.height;
    this->color = source.color;
}
```

But sometimes, what if we don't want to create the copy constructor for a class, then we use **delete** operator.

```c++
...
public:
    Rectangle() = default;
    Rectangle(const Rectangle& source) = delete;
...
```

Also, note that when we pass the a class object to a function without referencing it, then its value is copied using copy 
constructor.

## The Destructor

Destructors are special functions that are automatically called when our objects are being destroyed. This is the opportunity 
for us to free up space that our system is using. They are used when we work with files, streams etc.

```c++
// Header file
public:
    ~Rectangle(); // not a overloading function, only one destructor can be created in a class

// Source File
Rectangle::~Rectangle() {
cout << "Destructor Called";
}

// The above method will be called when our object will be destroyed.
```

## Static Members 

Now, when we create instances of classes we get separate objects with separate properties. But, we can also create the 
properties that won't be copied and can be used with the class itself. These are called **Static Members**.

```c++
// Header file
class Rectangle {
public:
...
static int getObjectsCount();

private:
...
static int objectsCount;
};

// Source file

Rectangle::Rectangle(int width, int height) {
objectsCount++;
setWidth(width);
setHeight(height);
}

int Rectangle::getObjectsCount() {
return objectsCount;
}



// Main file

cout << Rectangle::objectsCount << endl;
```

## Constant Objects and Functions

We can declare a class a const, and we won't be able to change the value of its members, and all the setters will not be
shown but with that other functions also can't be used that's when we use **const** keyword after function declaration to 
tell the compiler that we are not going to change the value of members in this function.


```c++
void Rectangle::draw() const {
    cout << "Drawing a rectangle..." << endl;
    cout << "Dimensions: " << width << ", " << height << endl;
}
```


## Array of objects

```c++
Rectangle rectangles[3] = {Rectangle(), Rectangle(10, 20), Rectangle(10, 20, "red")};

or

Rectangle rectangles[3] = {{}, {10, 20}, {10, 20, "red"}};
```

Note that, if you want to initialize an array of objects you have to create a default constructor in class if needed.


# Operator Overloading

## Overloading the Equality Operator

To create functions for operator overloading, we create a public method in header file with name operator followed by
sign of operator.

If, we overload == operator, then modern C++ compiler automatically creates inequality operator overload.

```c++
// Header file

class Point {
public:
    Point(int x, int y);

    bool operator==(const Point& other) const;

    int getX() const;
    int getY() const;
    void setX(int x);
    void setY(int y);
private:
    int x;
    int y;
};


// Source file
Point::Point(int x, int y) : x(x), y(y) {}

bool Point::operator==(const Point &other) const {
return (x == other.x) && (y == other.y);
}

// Main file

int main() {
Point pt1 {2, 3};
Point pt2 {2, 3};

if(pt1 == pt2) cout << "Equal";

return 0;
}

// Equal
```

## Comparison Operator

```c++
bool Length::operator<(const Length &other) const {
    return value < other.value;
}

bool Length::operator>(const Length &other) const {
    return value > other.value;
}

bool Length::operator<=(const Length &other) const {
    return !(value > other.value);
}

bool Length::operator>=(const Length &other) const {
    return !(value < other.value);
}
```

## Spaceship Operator

Creating every single comparison operator is tds, in above example we created comparison overloads for simple integers but
as we work with complex objects the cost of finding relationship using these operators increases. That's when in modern
C++ we use spaceship operator **<=>**, This operator has a return type of class **strong_ordering** and to compare that 
we can use its methods using **scope resolution operator** **::**

```c++
    int x = 10;
    int y = 10;
    
    strong_ordering result = x <=> y;
    
    if(result == strong_ordering::less) {
        ...
    }
```

Also, for our classes, compiler automatically generates the other comparison operators, if we overload the spaceship operator.
So, In modern C++, to compare objects we only need to overload two operators, == and <=>, and modern C++ compiler will
generate other operators for us.

## Overloading the stream insertion operator

In order to overload the steam insertion operator, we have to declare this function outside the header class because every
operator overload function thinks that the left value is the current object but when we use steam insertion operator the 
left object should always be **cout** and we can't compare **cout** with our object. Also, we need to return the reference to
the operator and we need to return the stream in the function so that we can use stream insertion operator many times.

```c++
ostream& operator<< (ostream& stream, const Length& length);

ostream& operator<< (ostream& stream, const Length& length) {
    return stream << length.getValue();
}
```

## Overloading the stream extraction operator

```c++
istream& operator>> (istream& stream, Length& length);

istream &operator>>(istream &stream, Length &length) {
    int value;
    stream >> value;
    length.setValue(value);
    return stream;
}
```

## Friends of Classes

There are times, we need to access the private properties or methods of a class like for the operators, we defined above.
In those cases, we have to add the definition of these functions in private methods of the class and prefix it with the
**friend** keyword.

```c++
class Length {
public:
    ...
private:
    int value;
    friend ostream& operator<< (ostream& stream, const Length& length);
};

ostream& operator<< (ostream& stream, const Length& length);
```

## Overloading the Arithmetic Operators

```c++
Length operator+ (const Length& other) const;

Length Length::operator+(const Length &other) const {
    return Length(value + other.value);
}
```

## Overload Compound Assignment Operators

```c++
Length& operator+= (const Length& other);

Length& Length::operator+=(const Length &other) {
    value += other.value;
    return *this;
}
```

## Overloading the Assignment Operator

Although, C++ compiler automatically overloads the assignment operator, but we can always change how an object is copied 
like we did for other overloading functions.

```c++
Length& operator= (const Length& other);

Length& Length::operator=(const Length &other) {
    value = other.value;
    return *this;
}
```

Note that, the assignment operator works differently at different tiems.

```c++
Length first {10};

// Copy constructor is called (NEW)
Length second = first;

// Assignment overload is called (EXISTING)
second = first;
```

## Overloading the Unary Operators

Increment and Decrement operators are unary operators which can be used as a prefix or a postfix.

```c++
Length& operator++(); // Prefix
Length& operator++(int); // Postfix

Length& Length::operator++() {
    value++;
    return *this;
}

Length Length::operator++(int) {
    Length copy = *this;
    operator++();
    return copy;
}
```

## Overloading the Subscript Operator

The subscript operator is the **[]** operator that we use to access the individual element of an array.

```c++
// Header file
class Array {
public:
    explicit Array(size_t size);
    ~Array();
    int& operator[](size_t index);
private:
    int* values;
    size_t size;
};

// Source file
#include <stdexcept>

Array::Array(size_t size) {
    values = new int[size];
    this->size = size;
}

Array::~Array() {
    delete[] values;
}

int& Array::operator[](size_t index) {
    if(index >= size) throw std::invalid_argument("index");
    return values[index];
}

```

## Overloading the Indirection Operator

We use Indirection Operator to dereference a pointer.

```c++
// Header file
class SmartPointer {
...
    int& operator*();
...
};

int& SmartPointer::operator*() {
    return *ptr;
}
```

## Overloading Type Conversions

```c++
// Header file public
operator int() const;

// Source file
Length::operator int() const {
return value;
}

// Main
Length length {10};
int x = length;
```

If we want to cast an object to integer before assigning it then we can mark the overload function as explicit.

```c++
// Header file public
explicit operator int() const;

// Main
Length length {10};
int x = static_cast<int> length;
```

## Inline Functions

So far, we are writing all our functions in source file or cpp file, but we can also write functions in header file.

```c++
int getValue() const {
    return value;
}
```

In above example, we are returning a value in a header file, and these are called **inline functions**.
It gives us a slight performance boost, because compiler converts these inline functions to their return value otherwise
its quite a overhead to go into a function and the go back the main function.

But, we should not define all functions in header files, because header files are used to describe the interface of our 
class and when we make any changes to header file, all the files related to it are recompiled so we should make it stable
as possible. So, to reduce the compilation time we should define all our logic in a cpp or a source file. 

The other reason for not defining functions in header file is because doing so causes clutter.

So, To create an inline function in our source file or cpp file, we can use the **inline** keyword before a function, but 
this is not guaranteed because it totally depends on the compiler. Also, use inline functions for very simple preferably
one liners functions because every time we call that function it will be replaced and if we have more than one line, the
size of file will increase and performance will decrease.

*Stay away from these technique, unless you know what you are doing*

Also, C++ Compiler will decide automatically whether it should make a function inline or not.

# Inheritance and Polymorphism

## Inheritance

**Inheritance** is a mechanism for reusing code so once we can implement common features in a base or parent class, and 
we can use its properties and methods in a child or derived class.

```c++
#include "Widget.h"

class TextBox : public Widget {
...
};
```

**public** here means that all the public members of parent class should be inherited as public members. If we use **private**
that means that public members of parent class will be inherited as private members of child class.

## Protected Members

**protected** is also one of the access modifiers, similarly like private its members can't be used outside a class but
we can be accessed in derived classes but private members can't.

Declare protected members only when you only need to use them in derived class, otherwise stay away. ☠️

## Constructors and Inheritance

In Inheritance, the base class constructor is called before the constructor of derived class.

To call the constructor of parent class in derived class.
```c++
TextBox::TextBox(const string& val, bool enabled) : Widget(enabled), value{value} {}
```

For creating constructors, that don't do anything but only passes values to base classes, we use parent class constructor, 
in child class.

```c++
class TextBox: public Widget {
public:
    using Widget::Widget();
private:
    ...
};
```

## Destructors and Inheritance

In Inheritance, destructors of derived classes are called before the destructors of base class.

## Conversion between base and derived classes

If we have an object created from a class which inherits another class, we can assign the value of that object to the parent
class and this is called **Up-casting**. but the other is not true, means Down-casting and its illegal.

Upcasting also works when we pass an object from derived class to a function where it takes parent class as argument.
When we pass the derived class object, the compiler has to discard some memory to copy an object. This is called **object**
**slicing**.

If, we use reference operator or a pointer in the function then no slicing happens and only members of parent class can be
called in a function.

## Overriding Methods

We can override the methods by initializing in the derived class and when we call the method which exists in both parent 
and child class, child class method will be called. If we pass a derived class to a function which take parent class as 
an argument then the method of parent class will be called. Even though we passing a child class object using reference, 
the compiler uses a technique called **static or early binding**. So at compile time, it knows that because we are working
with a parent class object, the draw method of widget class has to be called.

But, what if we have to use the method from the derived class that's when we use the **virtual** keyword. With this, we 
tell the compiler to use a different technique called **Late or Dynamic Binding**. So, at runtime, the compiler will decide
what draw method to call depending on the kind of object we are passing to the function.

```c++
// Widget

virtual void draw() const;

void Widget::draw() const {
cout << "Drawing a widget" << endl;
}

// Textbox

void TextBox::draw() const {
cout << "Drawing a textbox" << endl;
}

// Main

void showWidget(Widget& widget) {
    widget.draw();
}

showWidget(Textbox box); // Drawing a textbox
showWidget(Widget widget); // Drawing a widget
```

When overriding a base class method in derived class, its the best practice to use the virtual keyword.

Another best practice is to use the **override** keyword in base class method declaration for overriding functions, because
if we make any changes to the function in base class, the compiler will show us an error in the derived class.

```c++
class Widget {
public:
    virtual void draw(int number) const;
}

class TextBox : public Widget {
public:
void draw() const override; // ERROR
...
}
```

In above example, as we are not passing the parameters to the override method declaration, we get an error by using the
override keyword.

## Polymorphism

**Polymorphism** is also one of the main principal of OOP, and it allows us to create applications that can be easily
extended. 

Poly means Many and morphs means forms, so polymorphism means **many forms**. This refers to situation where an object
takes many forms.

If a function takes an object from a parent class, and we call that function and pass two different objects from classes
that inherits the same base class, in that case, the parameter of the function takes many forms.

## Polymorphic Conditions

```c++
// Early or Static Binding
vector<Widget> widgets;

vector.push_back(TextBox());
vector.push_back(CheckBox());

for(auto widget: widgets) {
    widget.draw(); // runs only widget draw method
}
```

```c++
// Dynamic or Late binding

vector<unique_ptr<Widget>> widgets;

vector.push_back(make_unique<TextBox()>);
vector.push_back(make_unique<CheckBox()>);

for(auto widget: widgets) {
    widget->draw(); // Drawing a textbox, Drawing a Checkbox
}
```

**vector<unique_ptr<Widget>> widgets;** is called the polymorphic collection so each object in this collection can take
a different form at runtime.

## Virtual Destructors

While destructing the objects, the instances of the derived classes are called first, and at last the destructor of parent
class is called. To destruct the parent class after every instance is destructed, we declare destructor of parent class
as **virtual** for late or dynamic binding.

So, here is the takeaway, whenever you add virtual methods to your class, you can have polymorphism somewhere in your project
so to destruct the objects properly use a virtual destructor even the destructor is not gonna do anything. If the destructor
is empty we can tell the compiler to generate a destructor by making it default.

```c++
virtual ~Widget = default;
```

## Abstract Classes

In above examples, in real world there will be different algorithms for drawing a widget, so we don't want to implement 
in widget class, but we want the user to implement that method in child class, that's when we assign the method declaration
to 0 and that is called a **pure virtual method** and we don't have to implement that method.

```c++
// Pure Virtual Method
virtual void draw() const = 0;
```

When, a class has at-east one **Pure Virtual Method** then we call it an abstract class, means we can't instantiate the
objects from that class but we can still use abstract classes as pointers or reference because we need them for polymorphic
behaviour.

So, Abstract Classes can't be instantiated they exists purely to be inherited and purely to provide some code to other classes.

Also, If we don't override the virtual method of an abstract class, then the derived class will be abstract as well.

So, If a method that we can't define in a pure meaningful way we should declare that method as pure virtual method by assigning
it to 0.

## Final Classes and Methods

Sometimes, we want some methods not to be overwritten in derived class, that's when we use **final** keyword.
```c++
class TextBox : public Widget {
public:
    void draw() const override final;
    ...
};
```

Now, we can't create a class that can override the draw method of TextBox class. 

But, we can also declare a class as final and that class can't be inherited by other classes.

```c++
class TextBox final : public Widget {
    ...
};
```

## Deep Inheritance Hierarchies

Too much of a good thing is a bad thing and deep inheritence among classes will make our code hard to understand. If we
make any change in parent class, all derived classes need to be changed because they all are coupled to their parent class.
And, If we make any changes to one class all the other classes needs to be recompiled. Limit the inheritance to maximum 
of 3 levels.

## Multiple Inheritance

In C++, a class can also have multiple base classes, this is called multiple inheritance. An example is **iostream**
inherits both **istream** and **ostream**.


```c++
// File Reader
class FileReader {
public:
FileReader(const string& fileName) {
cout << "Constructor of FileReader" << endl;
};

string fileName() {
return "fileName";
}

string read() {
return "Hello World";
};
};

// File Writer
class FileWriter {
public:
FileWriter(const string& fileName) {
cout << "Constructor of FileWriter" << endl;
};

string fileName() {
return "fileName";
}

void write(const string& content) {
cout << content;
}
};

// FileIO

#include "FileReader.h"
#include "FileWriter.h"

class FileIO: public FileReader, public FileWriter {
public:
FileIO(string fileName): FileReader(fileName), FileWriter(fileName) {}
};

// Main

int main() {
FileIO file {"fileName"};
file.FileReader::fileName();

return 0;
}
```

# Exceptions

## What are exceptions?

In programming, exceptions are objects that are used to report an error while our program is running.

## Throwing an exception

```c++
void Rectangle::setWidth(int width) {
    if(width < 0)
        throw invalid_argument("width");
    this->width = width;
}
```

## Catching an exception

```c++
void Rectangle::setWidth(int width) {
    if(width < 0)
        throw invalid_argument("The width can not be negative!");
    this->width = width;
}

int main() {
    try {
        cout << "Width: ";
        int width;
        cin >> width;

        Rectangle rect;
        rect.setWidth(width);
    }
    catch (const invalid_argument& ex) {
        cout << ex.what(); // ex.what() returns cstring of type const character pointer
    }

    return 0;
}
```

```console
Width: -1
The width can not be negative!
```

## Catching Multiple Exceptions

```c++
    void Rectangle::setWidth(int width) {
        if(width < 0)
            throw invalid_argument("The width can not be negative!");
    
        if(width > 100)
            throw out_of_range{"The width can not be greater than 100!"};
    
        this->width = width;
    }

    try {
        cout << "Width: ";
        int width;
        cin >> width;

        Rectangle rect;
        rect.setWidth(width);
    }
    catch (const invalid_argument& ex) {
        cout << ex.what();
    }
    catch (const out_of_range& ex) {
        cout << ex.what();
    }
```

Both **invalid_argument** and **out_of_range** errors are derived from same class called **logic_error**.
As we read about that, the derived class can be converted into parent class by upcasting but parent class can't be 
converted to derived class.

So, here to refactor this code, we can catch **logic_error** instead of catching other two errors.

```c++
catch (const logic_error& ex) {
    cout << ex.what();
}
```

If we want to change the logic of any catch block, then we have to order them according to their specificity.

_We can use only throw keyword in a function when we want to pass the exception to next function in call stack._

## Creating custom exceptions

```c++
class AccountLocked : public exception {
public:
    const char* what() const noexcept override {
        return "Your account is locked! Contact the admin...";
    }
};
```

**noexcept** is added to a function when a function doesn't throw any exception and also **noexcept** should be used
between **const** and **override** otherwise we will get a warning but the code will execute.

# Templates

## Function templates

Using function templates, we can define a function in a flexible way so it can work with any data type. So, our function
will be generic.

```c++
template<typename T>
T larger(T first, T second) {
    return (first > second) ? first : second;
}
```

Function templates can be also used to reduce the size of executable, so if we don't call this function the compiler will
not create the instance of this function. With overloading, we might be creating many functions but with templates the
compiler will create function that are used. For example, if we call the above function in above example, then the compiler
will either not create function or create a overload function if its used for multiple times.


## Explicit Type Arguments

There are times, when we have to define the value of **T**.
```c++
template<typename T>
T larger(T first, T second) {
    return (first > second) ? first : second;
}

larger(1.2, 1); // The compiler will throw error because first is double and other is int

larger<double>(1.2, 1); // The compiler will create the instance of function with double type.
```

## Templates with Multiple Parameters

```c++
template<typename K, typename V>
void display(K key, V value) {
    cout << key << "=" << value;
} 
```

## Templates in Classes

```c++
template<typename K, typename V>
class Pair {
private:
    K key;
    V value;
public:
    Pair(K key, V value);
    K getKey() const;
    V getValue() const;
};

template<typename K, typename V>
K Pair<K, V>::getKey() const {
    return key;
}

template<typename K, typename V>
V Pair<K, V>::getValue() const {
    return value;
}

template<typename K, typename V>
Pair<K, V>::Pair(K key, V value):key(key), value(value) {}
```

```c++
#include <cstddef>
#include <stdexcept>

template<typename T>
class Array {
public:
    explicit Array(size_t size);
    ~Array();
    T& operator[](size_t index);
private:
    T* values;
    size_t size;
};


template<typename T>
Array<T>::Array(size_t size) {
    values = new T[size];
    this->size = size;
}

template<typename T>
Array<T>::~Array() {
    delete[] values;
}

template<typename T>
T& Array<T>::operator[](size_t index) {
    if(index >= size) throw std::invalid_argument("index");
    return values[index];
}

// Main

Array<int> array{10};
array[0] = 1;

cout << array[0];

Array<Pair<string, int>> pairs {10};
pairs[0] = {"a", 1}; // as the type of array is Pair, the compiler will take these values and create a pair object.
```







