# Big O Problems
Caculate the time complexicity of a program.

## Thoughts
1.Big O problem mainly concentrate in how the programming works not how many recursions they have.

### Fabonacci Optimize Problem
Can be optimized in time complexity MIN -->O(N)

Fibonacci数列的时间复杂度取决于采用的计算方法。有多种方法可以计算Fibonacci数列，每种方法都具有不同的时间复杂度。以下是一些常见的方法和它们的时间复杂度：

1. Recursive method: The simplest method is to use recursion to calculate the Fibonacci sequence. However, the time complexity of this method is exponential, usually O(n^2). This is because when calculating the n-th Fibonacci number, the calculation of the n-1 and n-2 Fibonacci numbers will be recursively called, and so on, resulting in an exponential amount of calculation.

2. Dynamic programming method: Using dynamic programming can greatly reduce the time complexity of calculating the Fibonacci sequence. The time complexity of this method is O(n), where n is the position of the Fibonacci number to be calculated. Dynamic programming stores intermediate results in an array to avoid double calculations.

3. Matrix multiplication method: The time complexity can be further reduced through matrix multiplication, reducing it to O(log n). This method uses the properties of matrix multiplication to calculate the Fibonacci sequence, but requires some mathematical knowledge and the support of matrix operations.

In general, the time complexity of the Fibonacci sequence can be reduced from exponential O(2^n) to linear O(n), or even further reduced to logarithmic O(log n), depending on the selected calculation method. In practical applications, the appropriate calculation method should be selected based on specific needs and performance requirements.

#### Coding Example
```c
Recursive method:
int main()
{
    long aFunc(int n){
        if (n <= 1) return 1;
        else return aFunc(n - 1) + aFunc(n - 2);
    }
}
```
```c
Dynamic programming method:
int main()
{
    int Fibonacci(int n)
    {
        if (n <= 1)
            return n;
        else
        {
            int iter1 = 0;
            int iter2 = 1;
            int f = 0;
            for (int i = 2; i <= n; i++)
            {
                f = iter1 + iter2;
                iter1 = iter2;
                iter2 = f;
            }
            return f;
        }
    }
    return 0;
}

The space complexity is O(1)

Equivalent to reducing the size of the DP table from n to 2
Generally speaking, it is used to compress a two-dimensional DP table into one dimension, that is, to compress the space complexity from O(n^2) to O(n).
```
```c
Matrix multiplication method:
int main(){
    static int Fibonacci(int n){
        if (n <= 1)
            return n;
        int[, ] f = {{1, 1}, {1, 0}};
        Power(f, n - 1);
        return f[0, 0];
    }

    static void Power(int[, ] f, int n){
        if (n <= 1)
            return;
        int[, ] m = {{1, 1}, {1, 0}};
        Power(f, n / 2);
        Multiply(f, f);
        if (n % 2 != 0)
            Multiply(f, m);
    }

    static void Multiply(int[, ] f, int[, ] m){
        int x = f[0, 0] * m[0, 0] + f[0, 1] * m[1, 0];
        int y = f[0, 0] * m[0, 1] + f[0, 1] * m[1, 1];
        int z = f[1, 0] * m[0, 0] + f[1, 1] * m[1, 0];
        int w = f[1, 0] * m[0, 1] + f[1, 1] * m[1, 1];
        f[0, 0] = x;
        f[0, 1] = y;
        f[1, 0] = z;
        f[1, 1] = w;
    }
}
```