# kr_pavlova
№1
```
#include <iostream>
#include <vector>
#include <cmath>
#include <limits>

double calculateGeometricMean(const std::vector<int>& numbers) {
    double product = 1.0;
    int count = 0;
    
    for (int number : numbers) {
        if (number > 0 && number % 2 == 0) {
            product *= number;
            count++;
        }
    }
    
    if (count == 0) {
        return -1.0;
    }
    
    return std::pow(product, 1.0 / count);
}

int main() {
    int n;
    std::cin >> n;
    
    std::vector<int> numbers(n);
    
    for (int i = 0; i < n; i++) {
        std::cin >> numbers[i];
    }
    
    double geometricMean = calculateGeometricMean(numbers);
    
    if (geometricMean >= 0.0) {
        std::cout << geometricMean << std::endl;
    } else {
        int minValue = std::numeric_limits<int>::max();
        bool foundMinValue = false;
        
        for (int i = 0; i < n; i++) {
            if (i % 5 == 0 && numbers[i] < minValue) {
                minValue = numbers[i];
                foundMinValue = true;
            }
        }
        
        if (foundMinValue) {
            std::cout << minValue << std::endl;
        } else {
            std::cout << "No valid elements found." << std::endl;
        }
    }
    
    return 0;
}
```

№2
```
#include <iostream>
#include <string>

std::string transformString(const std::string& input) {
    std::string transformedString = input;
    bool foundDash = false;

    for (char& c : transformedString) {
        if (c == '-') {
            foundDash = true;
        } else if (foundDash) {
            c += 4;
        }
    }

    return transformedString;
}

int main() {
    std::string input;
    std::getline(std::cin, input);

    std::string transformed = transformString(input);
    std::cout << transformed << std::endl;

    return 0;
}
```

№3
```
#include <iostream>
#include <vector>

using namespace std;

double calculateAverage(const vector<vector<int>>& matrix, const vector<vector<bool>>& grayPositions) {
    int n = matrix.size();
    int sum = 0;
    int count = 0;

    for (int i = 0; i < n; ++i) {
        for (int j = 0; j < n; ++j) {
            if (!grayPositions[i][j]) {
                sum += matrix[i][j];
                ++count;
            }
        }
    }

    return static_cast<double>(sum) / count;
}

int main() {
    int n;
    cin >> n;

    vector<vector<int>> matrix(n, vector<int>(n));
    vector<vector<bool>> grayPositions(n, vector<bool>(n));

    for (int i = 0; i < n; ++i) {
        for (int j = 0; j < n; ++j) {
            cin >> matrix[i][j];
            grayPositions[i][j] = (i + j) % 2 == 0; // Закрашенные позиции имеют серый цвет
        }
    }

    double average = calculateAverage(matrix, grayPositions);
    cout << average << endl;

    return 0;
}
```

№4
```
std::cin >> n >> m;
int** arr = new int*[n];
for (int i = 0; i < n; i++) {
    arr[i] = new int[m];
}
pointers(arr, n, m);
for (int i = 0; i < n; i++) {
    for (int j = 0; j < m; j++) {
        std::cout << arr[i][j] << " ";
    }
    std::cout << std::endl;
}

// Освобождение памяти
for (int i = 0; i < n; i++) {
    delete[] arr[i];
}
delete[] arr;

return 0;
```

№5                    
```
void func(int& a, int b) {
    a -= b;
}
```

№6
```
struct shipment {
    int volume;
    int weight;
};

bool compare(const shipment& a, const shipment& b) {
    int volume_cost_a = a.volume / 5;
    int weight_cost_a = a.weight / 6;
    int final_cost_a = std::max(volume_cost_a, weight_cost_a);

    int volume_cost_b = b.volume / 5;
    int weight_cost_b = b.weight / 6;
    int final_cost_b = std::max(volume_cost_b, weight_cost_b);

    return final_cost_a > final_cost_b;
}
```
