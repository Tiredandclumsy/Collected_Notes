A radix, or base, is a value that governs a positional numeral system, defined as the number of unique digits in that numeral system. For example, decimal had radix 10, and thus is 'base-10'.

# Definition
A base-$b$ system represents all values using the digits $1, 2, \dots, b-1$. A string of such digits $$(a_n a_{n-1} \dots a_2 a_1 a_0 . c_1 c_2 \dots c_m)_b$$ represents the value $$a_n b^n + a_{n-1} b^{n-1} + \dots + a_2 b^2 + a_1 b^1 + a_0 b^0 + c_1 b^{-1} + c_2 b ^{-1} + \dots + c_m b^{-m}$$
# Converting between bases
To find any value in a base $b$, continually divide by $b$, noting any remainders, until the division yields 0. Then reverse the string of remainders. 

Proof:
Assume there exists some base-$b$ representation of a value $n$. Therefore $$n = (a_n \times b^k) + (a_{n-1} \times b^{k-1}) + ... + (a_2 \times b^2) + (a_1 \times b^1) + (a_0 \times b^0)$$$$n_1 = \frac n b = (a_n \times b^{k-1}) + (a_{n-1} \times b^{k-2}) + \dots + (a_2 \times b^1) + (a_1 \times b^0) \ r \ a_0$$$$n_2 = \frac {n_1} b = \frac n {b^2} = (a_n \times b^{k-2}) + (a_{n-1} \times b^{k-3}) + \dots + (a_2 \times b^0) \ r \ a_1$$$$\dots$$$$n_k = \frac {n_{k-1}} b = \frac n {b^k} = a_k \ r \ a_{k-1}$$$$n_{k+1} = \frac {n_k} b = \frac n {b^{k+1}} = 0 r a_k$$
It can be seen that this algorithm generates the digits $a_1, a_2, \dots, a_n$ of $n$ in reverse order.

# Common bases
Base-2 - Binary
Base-6 - Hex or Seximal
Base-8 - Octal
Base-10 - Decimal
Base-16 - Hexadecimal

#discrete-maths