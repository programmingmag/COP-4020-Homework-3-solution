# COP-4020-Homework-3-solution

Download Here: [COP 4020 Homework 3 solution](https://jarviscodinghub.com/assignment/cop-4020-homework-3-solution/)

For Custom/Original Work email jarviscodinghub@gmail.com/whatsapp +1(541)423-7793

Problem 1:
———-

In this problem you will write operations for an abstract data type Matrix,
by writing definitions for the module Matrix

==================================================================
module Matrix (Matrix, fillWith, fromRule, numRows, numColumns,
at, mtranspose, mmap, add, mult)
where

— newtype is like “data”, but has some efficiency advantages
newtype Matrix a = Mat ((Int,Int),(Int,Int) -> a)

fillWith :: (Int,Int) -> a -> (Matrix a)
fromRule :: (Int,Int) -> ((Int,Int) -> a) -> (Matrix a)
numRows :: (Matrix a) -> Int
numColumns :: (Matrix a) -> Int
at :: (Matrix a) -> (Int, Int) -> a
mtranspose :: (Matrix a) -> (Matrix a)
mmap :: (a -> b) -> (Matrix a) -> (Matrix b)
add :: Num a => (Matrix a) -> (Matrix a) -> (Matrix a)
mult :: Num a => (Matrix a) -> (Matrix a) -> (Matrix a)

— Without changing what is above, implement the above functions.
==================================================================

That is, you are to complete the module by writing a function definition
for each function declared in the module. To explain these, note that
an m x n matrix is one with m rows and n columns. Element indexes range
from 1 to the number of rows or columns (unlike the convention in C or
Haskell). With that convention you are to implement the following
functions:

– fillWith takes a pair (m,n) and an element e and produces an m x n
matrix each of whose elements are e.

– fromRule takes a pair (m, n) and a function g (the rule), and produces
an m x n matrix whose (i,j)th element is g(i,j).

– numRows takes an m x n matrix and returns the number of rows in the
matrix, m.

– numColumns takes an m x n matrix and returns the number of columns in
the matrix, n.

-at takes an m x n matrix and a pair of Ints, (i, j), and returns
the (i,j) th element of the matrix, provided that 1 <= i <= m and 1 <= j <= n. If either index is outside of those ranges, an error occurs (at runtime). - mtranspose takes an m x n matrix and returns an n x m matrix where the (i,j)th element of the result is the (j,i)th element of the argument matrix. - mmap takes an m x n matrix and a function f and returns an m x n matrix whose (i,j)th element is the result of applying f to the (i,j)th element of the argument matrix. - add takes two m x n matrices and returns an m x n matrix that is their sum. If the two matrices have different error, an error occurs (at runtime). - mult takes two matrices of shape m x n and m' x n' and returns an m x n' matrix that is their product. If the two matrices are not compatible, i.e., n /= m', an error occurs (at runtime). There are test cases contained in MatrixTests.hs. To aid in testing, we have also provided code to make Matrix an instance of the Haskell type classes Show and Eq. These instances are found in the file MatrixInstances.hs. To make the tests work, you have to put your code in a module named Matrix.

