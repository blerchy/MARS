MARS Timer Interrupt
====================

The purpose of this repository is to make a revision to [MARS](http://courses.missouristate.edu/KenVollmar/MARS/index.htm) publicly accessible.

This revision is contained in commit 1e7e9b5

```
Adds two new registers to Coprocessor 0:
- $9  (count)
- $11 (compare)

With each simulated instruction*, 1 is added to count. When count
and compare equal, a timer interrupt is raised, and Cause register
TI (bit 30) is set.

* Except in the case that Cause register DC is set to 1, in which
  case the count register is not incremented AND cause and compare
  are not compared with each other. i.e. no timer interrupt will
  be raised while DC is set

Timer interrupt implemented according to info in:
D. Sweetman, See MIPS run, 2nd ed. San Francisco, Calif:
    Morgan Kaufmann Publishers/Elsevier, 2007.
```
