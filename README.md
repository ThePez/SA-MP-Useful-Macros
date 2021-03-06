# SA-MP-Useful-Macros (v1.0)
[![sampctl](https://img.shields.io/badge/sampctl-SA--MP--Useful--Macros-2f2f2f.svg?style=for-the-badge)](https://github.com/The-Alex-Collins/SA-MP-Useful-Macros)

## Installation

Simply install to your project:

```bash
sampctl package install The-Alex-Collins/SA-MP-Useful-Macros
```

Include in your code and begin using the library:

```pawn
#include <u-macros>
```

## Usage
---
> CONNECTED
```pawn
// Example 1:
forward MyFunc(playerid);
public MyFunc(playerid)
{
  CONNECTED playerid
  {
    // ... Something will happend if playerid is connected
  }
  return 1;
}

// Example 2:
forward MyFunc(playerid);
public MyFunc(playerid)
{
  CONNECTED !playerid
  {
    // ... If playerid isn't connected
  }
  return 1;
}
```
---
> randomEx
```pawn
main()
{
  printf("%d", randomEx(2, 6));
  // Output: Random number between 2 and 6.
}
```
---
> error & debug
```pawn
#undef MAX_PLAYERS
#define MAX_PLAYERS 32

main()
{
  #if MAX_PLAYERS > 32
    // Example 1:
    error The number of max players must be 32! // Output: Error: The number of MAX_PLAYERS must be 32!
    // Example 2:
    error The number of max players must be %d!, MAX_PLAYERS // Output: Error: The number of MAX_PLAYERS must be 32!
    // Example 3:
    error "The number of max players must be %d!", MAX_PLAYERS // Output: Error: The number of MAX_PLAYERS must be 32!
  #endif
}
```
---
> CreateLabel
```pawn
// Without streamer
public OnGameModeInit()
{
  CreateLabel("text", 0xFFFFFFAA, 0.0, 0.0, 0.0, <30.0>);
  return 1;
}

// With streamer
public OnGameModeInit()
{
  CreateLabel("text", 0xFFFFFFAA, 0.0, 0.0, 0.0, <30.0>, <30.0>);
  return 1;
}
```
---
> Player Loop
```pawn
public OnPlayerConnect(playerid)
{
  PlayerLoop::<i>
  {
    // code...
  }
  return 1;
}
```
---
> Loop
```pawn
main()
{
  Loop::i<20>
  {
    print("This message will be printed 20 times.");
  }
}
```
---
> FUNCTION
```pawn
main()
{
	Test(20);
}

FUNCTION::Test<int>
{
	return printf("%d", int);
}
```
---
> FORMAT
```pawn
main()
{
  new string[20];
  FORMAT::(string, "%d", int);
  printf("%d", int);
}
```
---
## Testing

<!--
Depending on whether your package is tested via in-game "demo tests" or
y_testing unit-tests, you should indicate to readers what to expect below here.
-->

To test, simply run the package:

```bash
sampctl package run
```