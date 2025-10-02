[[1 - Alphabets]] <- Back
[[3 - Languages]] <- Next

---
## What are Strings?
Strings are sequences of symbols which are members of a given alphabet.
- Alphabets are used to form strings.

$$
\sum = \{a,b,c\}
$$
$$
w_{1} = aaa
$$
$$
w_{2} = aab
$$
$$
w_{3}=aac
$$
$w_1,w_2,w_3$ are all strings on the alphabet $\sum$ as they are formed STRICTLY of symbols from that alphabet.

## Concatenation
Concatenation is the combination of 2 given strings in an ordered way.

$$
\sum_{1} = \{a,b,c\}
$$
$$
\sum_2 = \{0, 1\}
$$
$$
w_{1} = aac, w_{2} = 01
$$

$$
w_1w_2 = aac01
$$
The order of strings in concatenation matters. The first string is prefixed to the next.
- So on until all strings concatenated. 

## Size/Length of String
The size/length of a string refers to how many symbols the string has.

$$
w_1 = aaa
$$
$$
|w_1| = 3
$$
## String Reversal
A string can be reversed. That means that, a given string...

$$
w = a_1a_2a_3...a_n
$$

When reversed, the new order of symbols is...

$$
w^R = a_n...a_3a_2a_1
$$

## Empty/Null String
The empty, aka null, string is a string with NO symbols.
- Because it has no symbols...
	- It has a size of 0.
	- It is a member of ALL languages and is formed from ALL alphabets.

Empty string denoted as $\lambda$.

## Substrings
A substring is a string within a string.

## Set of All Possible Strings of k size
Given an alphabet, a set of all possible strings of k size can be formed by...

$$
\sum.^k
$$
Let $\sum = \{a,b\}$

Then...

$$
\sum.^2 = \{aa,ab,ba,bb\}
$$

### IDENTITIES
1) The set of all possible strings length 0 of an alphabet equals the empty string.
$$
\sum.^0 = \{\lambda\}
$$
