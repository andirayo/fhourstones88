Fhourstones 8x8
===============

This version of Fhourstones supports bitboards beyond 64-bits,
as needed for the 8x8 size popular on littlegolem.net and itsyourturn.com.

It was used to solve the 8x8 game in the late 2014 and early 2015,
with the file book88 retaining all solved positions of at most 16 plies.

After running make, the program C488 repeatedly accepts lines containing digits 1-8,
and will solve the resulting position. An example session:

```
> make
g++ -std=c++11 -O3 -Wextra -Wall -DWIDTH=8 -DHEIGHT=8 -DBOOKWORK=24 -DLOCKSIZE=50 -DTRANSIZE=8306069 C4.cpp Search.cpp Window.cpp -o C488
> ./C488
444445555
Solving . . .    
score +  work 33  1 pos / 1 msec = 1 Kpos/sec
1111111188888888222222777777
Solving . . .    
score +  work 15  513960 pos / 153 msec = 3359 Kpos/sec
^D
Be seeing you...
```

Scores are given for the side to move; - = + for a lost, drawn, or won position, respectively.
Solutions requiring at least work BOOKWORK get permanently added to the opening book.
