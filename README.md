```
#include <cstdlib>
#include <string>
#include <sstream>
#include <iostream>


using namespace std;

static string error_message = "An error has occured while reading input data\n";

int main()
{
    const  char size= 10;
    int array[size];
    int summ=0;
    string input_str;
    getline(cin, input_str);
    istringstream stream(input_str);
    for (int i=0; i < size; i++)
    {
        if (!(stream >> array[i]))
        {
            cerr << error_message;
            exit( EXIT_FAILURE);
        }
    }
    int test;
    if (stream >> test ){
        cerr << error_message;
        exit( EXIT_FAILURE);
    }
    for (int i=0; i < size; i++)
    {
        for (int j=i; j < size; j++)
        {
            if (array[i] > array[j])
            {
                summ++;
            }
        }
    }

    cout << "\n" << summ;
    return 0;
}
```
