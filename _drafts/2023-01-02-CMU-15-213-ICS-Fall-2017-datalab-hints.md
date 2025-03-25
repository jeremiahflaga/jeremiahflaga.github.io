---
title: "Hints for CMU 15-213 ICS (Fall 2017) Lab 1: datalab"
excerpt: 
date: 2023-01-02 12:00:00 AM UTC
tags: 
  - CSAPP
  - "Computer Systems: A Programmer's Perspective"
  - Randal Bryant
  - David O'Hallaron
  - CMU 15-213 Introduction to Computer Systems
  - Carnegie Mellon University
  - self-taught programmer
  - teach yourself computer science
  - teachyourselfcs.com
  - learncs.me
published: false
---

<style>
.table-witdth-50-percent{
    width: 50%;
}
</style>

## bitXor

``` c
/* 
 * bitXor - x^y using only ~ and & 
 *   Example: bitXor(4, 5) = 1
 *   Legal ops: ~ &
 *   Max ops: 14
 *   Rating: 1
 */
int bitXor(int x, int y) {
  return 2;
}
```

Hints:

Idea from when I took Nand2Tetris: [Hints for Nand2Tetris Chapter 1 Exercises](https://jboyflaga2.blogspot.com/2017/02/Nand2Tetris-Chapter1-Hints.html)  (refer to what is called Canonical Representation)

{: .table-witdth-50-percent }
x | y | x XOR y
--|---|--------
0 | 0 |    0
0 | 1 |    1
1 | 0 |    1
1 | 1 |    0

x XOR y = (!x AND y) OR (x AND !y)



## tmin

``` c
/* 
 * tmin - return minimum two's complement integer 
 *   Legal ops: ! ~ & ^ | + << >>
 *   Max ops: 4
 *   Rating: 1
 */
int tmin(void) {
  return 2;
}
```

TMin is 1 followed by 0s.




/*
 * isTmax - returns 1 if x is the maximum, two's complement number,
 *     and 0 otherwise 
 *   Legal ops: ! ~ & ^ | +
 *   Max ops: 10
 *   Rating: 1
 */
int isTmax(int x) {
  return 2;
}