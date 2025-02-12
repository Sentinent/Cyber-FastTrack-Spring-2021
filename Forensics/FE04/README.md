# FE04
> 100pt

## Briefing
> Download the file and filter down to the username according to criteria below.

> The username you are looking for has `x` as the 3rd character, followed immediately by a number from `2` to `6`, it has a `Z` character in it and the last character is `S`.

> When you have the username, submit it as the flag.

## Solution
The provided file can be found [here](fe04.zip).

Grep on steriods, let's break it down step by step.

We have the criteria of:
- has x as the 3rd character
- a number from 2-6 immediately after
- contains the character `Z`
- finishes off with `S`
So, there's this cool command called grep, where you can search for certain expressions. I grepped the inital file for anything that met one of the first 3 requirements, and then piped it out to another file, to rinse and repeat. After satisfying the first 3 requirements, I manually removed everything left that didn't finish with `S`, leaving me with 6 strings. Finally, I had a read through the 6 to see what one was right, and submitted it as the flag, commands used below:
```
grep -ex2 -ex3 -ex4 -ex5 50k-users.txt > step1.txt
grep 'Z' step1.txt > step2.txt
grep "S" step2.txt > final.txt
```

## Flag
Flag: `YXx52hsi3ZQ5b9rS`
