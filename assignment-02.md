# CMPS 2200 Assignment 2

**Name:**_________________________

In this assignment we'll work on applying the methods we've learned to analyze recurrences, and also see their behavior
in practice. As with previous
assignments, some of of your answers will go in `main.py` and `test_main.py`. You
should feel free to edit this file with your answers; for handwritten
work please scan your work and submit a PDF titled `assignment-02.pdf`
and push to your github repository.


1. Derive asymptotic upper bounds of work for each recurrence below.
  * $W(n)=2W(n/3)+1$
  * since n^(log_3(2))>n^0
  * it's leaf dominated
  * the work is O(n^(log_3(2)))
.  
.  
.  
.  
  * $W(n)=5W(n/4)+n$
  * since n^(log_4(5))>n
  * it's leaf dominated
  * the work is 0(n^(log_4(5)))
.  
.  
.  
.  
.  
  * $W(n)=7W(n/7)+n$
  * since n^(log_7(7))=n
  * it's balance
  * depth=logn
  * the work is O(nlogn)
.  
.  
.  
.  
.  
  * $W(n)=9W(n/3)+n^2$
  * since n^(log+3(9))=n^2
  * it's balance
  * the work is O(n^2logn)
.  
.  
.  
.  
.  
  * $W(n)=8W(n/2)+n^3$
  * since n^(log_2(8))=n^3
  * it's balance
  * the work is 0(n^3logn)
.  
.  
.  
.  
.  
  * $W(n)=49W(n/25)+n^{3/2}\log n$
  * n^(log_25(49))<n^(3/2)logn
  * root dominated
  * the work is 0(n^(3/2)logn)
.  
.  
.  
.  
.  
  * $W(n)=W(n-1)+2$
  * Depth is n
  * work is O(n)
.  
.  
.  
.  
.  
  * $W(n)= W(n-1)+n^c$, with $c\geq 1$
  * depth is n
  * work is O(n^(c+1))
.  
.  
.  
.  
.  
  * $W(n)=W(\sqrt{n})+1$
  * let k = log(n)
  * n=2^k
  * W(2^k)=W(2^(k/2))+1
  * let V(k)=W(2^k)
  * V(k)=V(k/2)+1
  * it's leaf dominated
  * work is log(k)
  * and k=log(n)
  * work is log(log(n))


2. Suppose that for a given task you are choosing between the following three algorithms:

  * Algorithm $\mathcal{A}$ solves problems by dividing them into
      five subproblems of half the size, recursively solving each
      subproblem, and then combining the solutions in linear time.
    
  * Algorithm $\mathcal{B}$ solves problems of size $n$ by
      recursively solving two subproblems of size $n-1$ and then
      combining the solutions in constant time.
    
  * Algorithm $\mathcal{C}$ solves problems of size $n$ by dividing
      them into nine subproblems of size $n/3$, recursively solving
      each subproblem, and then combining the solutions in $O(n^2)$
      time.

    What are the asymptotic running times of each of these algorithms?
    Which algorithm would you choose?

    A: W(n)=5(n/2)+O(n)
       S(n) = S(n/2) + O(n) = O(n)
    it's leaf dominated, runtime is O(n^(log_2(5)))
    B: W(n)=2(n-1)+O(1)
       S(n)=(n-1)+O(1)
    it's leaf dominated, runtime is O(2^n)
    C: W(n)=9(n/3)+O(n^2)
       S(n)=(n/3)+O(n^2)
    it's balance, runtime is O(n^2logn)

    I wil choose algorithm A since it's has the fastest runtime


3. Now that you have some practice solving recurrences, let's work on
  implementing some algorithms. In lecture we discussed a divide and
  conquer algorithm for integer multiplication. This algorithm takes
  as input two $n$-bit strings $x = \langle x_L, x_R\rangle$ and
  $y=\langle y_L, y_R\rangle$ and computes the product $xy$ by using
  the fact that $xy = 2^{n/2}x_Ly_L + 2^{n/2}(x_Ly_R+x_Ry_L) +
  x_Ry_R.$ Use the
  stub functions in `main.py` to implement Karatsaba-Ofman algorithm algorithm for integer
  multiplication: a divide and conquer algorithm that runs in
  subquadratic time. Then test the empirical running times across a
  variety of inputs in `test_main.py` to test whether your code scales in the manner
  described by the asymptotic runtime. Please refer to Recitation 3 for some basic implementations, and Eqs (7) and (8) in the slides https://github.com/allan-tulane/cmps2200-slides/blob/main/module-02-recurrences/recurrences-integer-multiplication.ipynb
 
 


