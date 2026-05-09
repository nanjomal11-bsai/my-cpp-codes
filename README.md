```cpp
 C++ Programs Collection 
________________________________________
Program 1: Frequency of Each Number in Array
Description: Counts how many times each unique number appears in the array.
```cpp
Code:
#include <iostream>
using namespace std;

int main(){
    int size;
    cout<<"Enter size ";
    cin >> size;

    int arr[size];
    int freq[size] = {0};

    cout << "Enter elements" << endl;
    for(int i=0; i<size; i++)
        cin >> arr[i];

    cout << "Frequency of each unique number" << endl;

    for(int i=0; i<size; i++){
        int count=1;
        for(int j=i+1; j<size; j++){
            if(arr[i]==arr[j]){
                freq[j]=1;
                count++;
            }
        }
        if(freq[i]==0){
            cout << "Number "<<arr[i]<<" comes "<<count<<" times" << endl;
        }
    }
    return 0;
}
```
Sample Output:
Enter size 5
Enter elements
1 2 2 3 1
Frequency of each unique number
Number 1 comes 2 times
Number 2 comes 2 times
Number 3 comes 1 times
________________________________________

Program 2: Reverse a String (Using Pointers)
Description: Reverses a string using pointer manipulation.
```cpp
Code:
#include <iostream>
using namespace std;

string reverse (string str){
    int start =0, end =str.length();
    char* ptr = &str[0];

    while (start < end){
        end--;
        int temp = *(ptr+start);
        *(ptr+start)=*(ptr+end);
        *(ptr +end)=temp;
        start++;
    }
    return str;
}

int main (){
    string str;
    cout << "Enter string: ";
    getline(cin, str);

    cout << reverse(str);
}
```

Sample Output:
Enter string: hello
olleh
________________________________________
Program 3: Bubble Sort (Using Pointers)
Description: Sorts an array in ascending order using Bubble Sort with pointers.
Code:
```cpp
#include<iostream>
using namespace std;

void bubblesort(int arr[]){
    int* ptr=&arr[0];

    for (int i=0; i<5-1; i++){
        for(int j=0; j<5-1-i; j++){
            if(*(ptr+j)>*(ptr+j+1)){
                int temp = *(ptr+j);
                *(ptr+j)=*(ptr+j+1);
                *(ptr+j+1)=temp;
            }
        }
    }
}

int main(){
    int arr[]={7,8,6,3,5};

    cout << "UnSorted Array :" << endl;
    for (int i=0; i<5; i++){
        cout<<arr[i]<<" ";
    }

    bubblesort(arr);

    cout << "\nSorted Array " << endl;
    for(int i=0; i<5; i++){
        cout<<arr[i]<<" ";
    }
}
```
Sample Output:
UnSorted Array :
7 8 6 3 5
Sorted Array
3 5 6 7 8
________________________________________

Program 4: Search Element in Array
Description: Searches for a number in the array and returns its index if found.

```cpp
Code:
#include <iostream>
using namespace std;

int main(){
    int arr[10];
    int* ptr = arr;

    cout << "Enter any 10 Elements of Array :" << endl;
    for (int i=0; i<10; i++){
        cin>>*(ptr+i);
    }

    cout << "Elements of Array are :" << endl;
    for (int i=0; i<10; i++){
        cout<<*(ptr+i) << " ";
    }

    int search, index=-1;
    cout << endl << "Enter number you want to search: ";
    cin >> search;

    for (int i=0; i<10; i++){
        if(*(ptr+i)==search){
            index = i;
        }
    }

    if(index != -1){
        cout << "\nElement found at index " << index << endl;
    } else {
        cout << "The searched element is not found";
    }

    return 0;
}
```
Sample Output:
Enter elements: 1 2 3 4 5 6 7 8 9 10
Enter number you want to search: 5
Element found at index 4
________________________________________

```cpp
Program 5: Swap Two Numbers (Using Pointers)
Description: Swaps two numbers using pointers.
Code:
#include <iostream>
using namespace std;

void swap(int* ptr1, int* ptr2){
    int temp = *ptr1;
    *ptr1 = *ptr2;
    *ptr2 = temp;
}

int main(){
    int a = 5, b = 10;

    cout << "Before swapping" << endl;
    cout << "a = " << a << endl << "b = " << b << endl;

    swap(&a, &b);

    cout << "After swapping" << endl;
    cout << "a = " << a << endl << "b = " << b << endl;

    return 0;
}
```
Sample Output:
Before swapping
a = 5
b = 10
After swapping
a = 10
b = 5
```

