# Algorithm and Data Structure 
This is a repository of various algorithm and data structure problems.
## Maximum Pairwise Product
Find the maximum product of two distinct numbers in a sequence of non-negative integers. <br /> 
**Input:** A sequence of non-negative integers. <br />
**Output:** Maximum value that can be obtained by multiplying two different elements from the sequence. <br />
### Sample
**Input:**  <br /> 
```cpp
3
3 4 6
```
**Output:**  <br /> 
```cpp
24
```
### Code
```cpp
#include <iostream>
#include <vector>
#include <algorithm>

long long MaxPairwiseProduct(const std::vector<int>& numbers) {
	long long max_product = 0;
	int n = numbers.size();
	int first_index = 0;
	int second_index = 0;
	long long first_num = 0;
	long long second_num = 0;
	for (int first = 0; first < n; ++first) {
		if (numbers[first]>first_num){
			first_num = numbers[first];
			first_index = first;
		}
	}
	for (int second = 0; second < n; ++second) {
		if (numbers[second]>second_num & second != first_index){
			second_num = numbers[second];
			second_index = second;
		}
	}


    return first_num*second_num;
}

int main() {
    int n;
    std::cin >> n;
    std::vector<int> numbers(n);
    for (int i = 0; i < n; ++i) {
        std::cin >> numbers[i];
    }

    std::cout << MaxPairwiseProduct(numbers) << "\n";
    return 0;
}
```
