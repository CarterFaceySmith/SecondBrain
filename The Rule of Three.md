# The Rule of Three

AKA the law of three, the big three

A rule of thumb mainly to keep your code handy-dandy and safe from errors.

### The rule itself
If a class defines any of the following then it should explicitly define all three:
1. destructor;
2. copy contructor; or a
3. copy assignment operator.

### But why?
Basically, the rule claims that if one of these had to be defined by you then the others likely don't fit the needs of the class in one case and therefore won't in others either so should be redefined for your specific cases.

### The Rule of Five
Sometimes broadened to the rule of five, this is simply the rule above but including the move constructor and move assignment operator.

See also:
- [[C++]]