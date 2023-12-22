#include <iostream>

using namespace std;

// Function to count set bits in binary representation
int countSetBits(int num) {
    int count = 0;
    while (num > 0) {
        count += num % 2;
        num /= 2;
    }
    return count;
}

int main() {
    // User input
    int n, k;
    cin >> n >> k;

    // Check if there exists a number less than or equal to N with exactly K set bits
    bool existsNumber = false;
    for (int i = 0; i <= n; ++i) {
        if (countSetBits(i) == k) {
            existsNumber = true;
            break;
        }
    }

    // Output
    cout << (existsNumber ? "Yes" : "No") << endl;

    return 0;
}
