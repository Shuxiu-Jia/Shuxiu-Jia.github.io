+++
date = '2025-01-15T12:57:58+08:00'
draft = true
title = 'Stanford Cs106L Notes'
+++
[Stanford CS106L textbook](https://cs106l.github.io/textbook/)

---

## Lec 1 - Welcome
Why C++
> The invisible foundation of everything

C++ is great for…
- Handling lots of data
- And handling it very efficiently
- And doing it in an elegant, readable way


C++ History:
- invention of c:
    - Dennis Ritchie created C in 1972 to much praise
    - Compilers: Source Code → Assembly
    - “When I read C I know what the output Assembly is going to look like”
    - Weeknesses:
        - No objects or classes
        - Difficult to write generic or templated code
        - Tedious to write large programs
- Welcome to C++
    - In 1983, the beginnings of C++ were created by Danish computer scientist Bjarne Stroustrup
    - Had high level features

> "Code should be elegant and efficient; I hate to have to choose between those" —Bjarne Stroustrup

C++ Design Philosophy
- Express ideas and intent directly in code.
- Enforce safety at compile time whenever possible.
- Do not waste time or space.
- Compartmentalize messy constructs.
- Allow the programmer full control, responsibility, and choice.

C++ helps develop good coding hygiene
- Am I using objects the way they’re meant to be used?
    - Type checking, type safety
- Am I using memory efficiently?
    - Reference/copy semantics, move semantics
- Am I modifiying something I’m not supposed to?
    - const and const correctness
- Other languages relax these restrictions

---

## Lec 2 - Type And Structs
Why compile over interpret?
- It allows us to generate more efficient machine code!
    - Interpreters only see one small part of code at a time
    - Compilers see everything
- However, compilation takes time!

**C++ is a compiled language**
 Aside: “compiled language” is a misleading term

### Type
 **C++ is a statically typed language**
 -  Every variable must declare a type
 - Once declared, the type cannot change

### Struct
Structs bundle data together into a single object
```c++
struct StanfordID {
    string name; // These are called fields
    string sunet; // Each has a name and type
i   nt idNumber;
};

StanfordID id; // Initialize struct
id.name = "Jacob Roberts-Baca"; // Access field with ‘.’
id.sunet = "jtrb";
id.idNumber = 6504417;

StanfordID fi { ”Fabio Ibanez",”fibanez", 6504418 }; // List Initialization
```

**std::pair is a general purpose struct with two fields**
```c++
template <typename T1, typename T2>
struct pair {
    T1 first;
    T2 second;
};
std::pair<std::string, int>

struct pair {
    std::string first;
    int second;
};
```

**#include from the C++ Standard Library to use built-in types
And use the std:: prefix too!**

std ― The C++ Standard Library
``` c++
// Solving a Quadratic Equation
std::pair<bool, std::pair<double, double>> solveQuadratic(double a, double b, double c);
```
- Quality of life features to improve your code
    - using creates type aliases
    - auto infers the type of a variable
``` c++
#include <iostream>
#include <utility>

#include <cmath>

using Zeros = std::pair<double, double>;    // using is kind of like a variable for types
using Solution = std::pair<bool, Zeros>; 

/**
 * Solves the equation ax^2 + bx + c = 0
 * @param a The coefficient of x^2
 * @param b The coefficient of x
 * @param c The constant term
 * @return A pair. The first element (bool) indicates if the equation has a solution.
 *                 The second element is a pair of the roots if they exist.
 */
Solution solveQuadratic(double a, double b, double c)
{
  // Your code here...
  double discrim = b * b - 4 * a * c;
  if (discrim < 0) return { false, { 106, 106 }};

  double root = sqrt(discrim);
  return { true, { (-b - root) / (2 * a), (-b + root) / (2 * a) }};
}

int main() {
  // Get the values for a, b, and c from the user
  double a, b, c;
  std::cout << "a: "; std::cin >> a;
  std::cout << "b: "; std::cin >> b;
  std::cout << "c: "; std::cin >> c;

  // Solve the quadratic equation, using our quadratic function above
  auto result = solveQuadratic(a, b, c);
  if (result.first) {
    auto solutions = result.second; // The auto keyword tells the compiler to infer the type
    std::cout << "Solutions: " << solutions.first << ", " << solutions.second << std::endl;
  } else {
    std::cout << "No solutions" << std::endl;
  }

  return 0;
}
```

to be solved ??? std:: pair