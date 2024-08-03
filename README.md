
#include <iostream>
using namespace std;

class linear_search 
{ 
public:
    int a[10], n;

    void accept(int n)
    {
        cout << "Enter " << n << " elements:\n ";
        for(int i = 0; i < n; i++)
        {
            cout<<"enter Element:";
            cin >> a[i];
        }
        cout<<"unsorted array:\n";
        for(int i=0;i<n;i++)
        {
            cout<<a[i]<<"\t";
        }
    }

    void sort(int n)
    {
        int temp;
        for(int i = 0; i < n; i++)
        {
            for(int j = 0; j < n-1; j++)
            {
                if(a[j] > a[j+1])
                {
                    // Swap a[j] and a[j+1]
                    temp = a[j];
                    a[j] = a[j+1];
                    a[j+1] = temp;
                }
            }
        }
        cout<<"\nsorted array:\n";
        for(int i=0;i<n;i++)
        {
            cout<<a[i]<<"\t";
        }
    }

    void search(int n, int target)
    {
        int found = 0;
        for(int i = 0; i < n; i++)
        {
            if(target == a[i])
            {
                cout << "\nElement found at index " << i ;
                found = 1;
                break;
            }
        }
        if(found!=1)
        {
            cout << "\nElement not found" << endl;
        }
    }
};

int main()
{  
    linear_search s;
    int n, target;

    cout << "Enter size of array: ";
    cin >> n;

    s.accept(n);
    s.sort(n);

    cout << "\nKey to search: ";
    cin >> target;

    s.search(n, target);

    return 0;
}
