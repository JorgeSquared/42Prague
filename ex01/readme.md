# How to solve? Some suggestions

This is a little guide for those who are stuck when solving the **Exercise 01: testShell00** exercise from **C Piscine Shell 00**. To see the exact problem specification, please go to https://cdn.intra.42.fr/pdf/pdf/128738/en.subject.pdf


# What does the exercise want you to do?

Maybe, you are not getting the goal of the exercise. To put it simply, the line
```
r--r-xr-x 1 XX XX 40 Jun 1 23:42 testShell00
```
just wants you to change the accessibility of the `testShell00` file so that the owner can read it, and other groups can read and execute. That's the hint!


## How to?

See the `man` page of the `chmod` command. Hint: try the following commands on a random file:
```
chmod go+ x someFile
```
and then check out the `ls -l` command

## Where to go from here?

This was the "symbolic" way of changing accessibility. The other way to solve this is the "octal" or "numeric" way. There are three groups, each of which can have three different accessibility states: read. Suppose for a while that a 3-bit binary number represents the three possible states for just one group: `100 = read`, `010 = write` and `001 = execute`. Now experiment a bit: in this setting, concatenating three groups of 3-bit binary numbers each representing one group, we can obtain something like:
```
110011100 = (110)(011)(100) = -(rw-)(-wx)(r--) = 634
```
You got it? Will experiment with it further?


