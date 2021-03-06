# Common AVR Functions
Copy-pastable code blocks I often find useful

## Global Variables
They must be volatile if they are to be changed from anywhere in the code.
```C
volatile int intensity=123;
```

## Delay Functions
It's best not to add `_delay_ms()` or `_delay_us()` more than once in a file. They're large and bloat the code. Instead, loop them over. It's slightly less inaccurate, but likely doesn't matter for your application.

```c
#include <util/delay.h>
void WaitMs(int ms){while(ms-->0) _delay_ms(1);}
void WaitUs(int us){while(us-->0) _delay_us(1);}
```
