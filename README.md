# kr_pavlova
№1
#include <iostream>
#include <cmath>

using namespace std;

double f(double x) {
    if (x > 6) {
        if (2-x>0) {
            return 7 * pow(x, 5) - pow(2 - x, 1.0 / 5);
        }
        else {
            return 7 * pow(x, 5) + pow(x-2, 1.0 / 5);
        }
    } else if (-3 < x && x <= 6) {
        return pow(5, -3 * x) + 2;
    } else {
        if (4 - pow(x, 2) != 0) {
            return 2 * x / abs(4 - pow(x, 2));
        } else {
            return 2*x;
        }
    }
}

int main() {
    double x;
    cin >> x;

    double result = f(x);
    cout << result << endl;

    return 0;
}
  
№2
#include <iostream>
#include <cmath>

using namespace std;

int main() {
    int n;
    cin >> n;

    double sum = 0;
    double factorial = 1;
    for (int k = 1; k <= n; k++) {
        factorial *= k;
        sum += factorial / pow(k, 5);
    }

    cout.precision(10);
    cout << sum << endl;

    return 0;
}
                       
№3
#include <iostream>
using namespace std;

int main() {
    double a;
    cin >> a;
    
    double sum = 0.0;
    int n = 1;
    
    while (sum <= a) {
        sum += 1.0 / n;
        n++;
    }
    
    cout << n-1 << endl;
    
    return 0;
}
 
№4
#include <iostream>
#include <cmath>

using namespace std;

int main() {
    double m;
    cin >> m;

    double a, a_prev = 7.0;
    int n = 1;

    while (true) {
        a = a_prev + cos(a_prev + 4);
        n++;
        if (abs(a - a_prev) < m) {
            break;
        }
        a_prev = a;
    }

    cout << n << endl;

    return 0;
}

                    
№6
#include <iostream>
using namespace std;

bool half(int a, int b) {
    return a == 2 * b;
}

int main() {
    int a, b;
    cin >> a >> b;
    cout << half(a, b) << endl;
    return 0;
}
  
  
№5
#include <iostream> 
using namespace std;
#include <cmath> 

int main()
{
	int n;
	cin >> n;
	int* arr = new int[n];
	int geometric_mean = 1;
	int count_mean = 0;
	int maximum = -9999;
	bool flag = false;
	for (int i = 0; i < n; i++)
	{
		cin >> arr[i];
		if (arr[i] >= 0 and arr[i] % 8 == 0)
		{
			if (arr[i] > 0 and arr[i] % 8 == 0)
			{
				geometric_mean *= arr[i];
				count_mean++;
				flag = true;
			}
		}
		if ((i + 1) % 5 == 0 and arr[i] > maximum
			)
		{
			maximum = arr[i];
		}
	}
	if (flag)
	{
		cout << pow((fabs(geometric_mean)), (1.0 / count_mean)) << endl;
	}
	else
	{
		cout << maximum << endl;
	}
	return 0;
}
