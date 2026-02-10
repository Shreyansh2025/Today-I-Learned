# How to Read Files in C++ (fstream)

**Project:** Huffman Compressor
**Date:** 2026-02-11

### The Problem
I needed to read a text file (`input.txt`) character by character, including spaces and newlines, to count frequencies.

### The Solution
Use the `<fstream>` library.
* `ifstream`: Stands for "Input File Stream" (for reading).
* `.get(ch)`: Reads EVERY character. (Note: Using `file >> ch` is wrong because it skips spaces!).

### Code Example
```cpp
#include <fstream>
#include <iostream>
using namespace std;

int main() {
    // 1. Open the file
    ifstream inputFile("input.txt");

    // 2. Check if it actually opened
    if (!inputFile) {
        cout << "Error: File not found!" << endl;
        return 1;
    }

    char ch;
    // 3. Loop through every character
    // .get() returns false when it hits End of File (EOF)
    while (inputFile.get(ch)) {
        cout << ch; // Print or process the character
    }

    // 4. Always close the file
    inputFile.close();
    return 0;
}
