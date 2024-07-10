Bitwise operations in [[C++]] are operations that directly manipulate bits at the [[Computer Binary]] level. This is normal only done in codebases where [[Optimisation]] is a key consideration.

## All The Lovely Bitwise Operations

### 1. Bitwise AND (`&`)

The bitwise AND operation compares each bit of two operands and produces a result of `1` if both bits are `1`, otherwise `0`.

**Example:**
```cpp
int a = 5;    // Binary: 0101
int b = 3;    // Binary: 0011

int result = a & b;  // result is 0001 (which is 1 in decimal)
```

### 2. Bitwise OR (`|`)

The bitwise OR operation compares each bit of two operands and produces a result of `1` if at least one of the bits is `1`.

**Example:**
```cpp
int a = 5;    // Binary: 0101
int b = 3;    // Binary: 0011

int result = a | b;  // result is 0111 (which is 7 in decimal)
```

### 3. Bitwise XOR (`^`)

The bitwise XOR (exclusive OR) operation compares each bit of two operands and produces a result of `1` if the bits are different, otherwise `0`.

**Example:**
```cpp
int a = 5;    // Binary: 0101
int b = 3;    // Binary: 0011

int result = a ^ b;  // result is 0110 (which is 6 in decimal)
```

### 4. Bitwise NOT (`~`)

The bitwise NOT operation is a unary operation that inverts all the bits of its operand.

**Example:**
```cpp
unsigned int a = 5;    // Binary: 0000 0000 0000 0000 0000 0000 0000 0101

unsigned int result = ~a;  // result is 1111 1111 1111 1111 1111 1111 1111 1010
```

### 5. Bitwise Left Shift (`<<`) and Right Shift (`>>`)

Bitwise left shift (`<<`) and right shift (`>>`) operations shift the bits of a number to the left or right by a specified number of positions.

**Examples:**
```cpp
int a = 5;    // Binary: 0101

int result_left = a << 1;   // result is 1010 (which is 10 in decimal)
int result_right = a >> 1;  // result is 0010 (which is 2 in decimal)
```

## What Would you Even Use This For?

### 1. Checking if a Number is Even or Odd
```cpp
int num = 6;
if (num & 1) {
    cout << "Odd";
} else {
    cout << "Even";
}
// Output: Even
```

### 2. Efficiently Multiplying/Dividing by Powers of 2
```cpp
int num = 10;
int result_multiply = num << 2;   // Multiply by 4
int result_divide = num >> 1;     // Divide by 2
```

### 3. Setting and Clearing Bits
```cpp
// Set a bit at position 3
int bitmask = 1 << 3;

// Clear a bit at position 2
bitmask &= ~(1 << 2);
```