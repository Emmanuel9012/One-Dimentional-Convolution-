# One-Dimentional-Convulution
Explanation of 1D Convolution
Convolution is a mathematical operation that combines two signals to produce a third signal. In 1D convolution, we take an input signal and an impulse response (or kernel) and slide (or convolve) the kernel over the input signal to produce an output signal.

The formula for the convolution of two discrete signals x[n] and h[n] is given by:
y[n] = ∑ (from k=0 to M) x[k] * h[n - k]
Where:

y[n] is the output signal.
x[k] is the input signal.
h[n-k] is the impulse response.
M is the number of samples in the impulse response minus one.
Steps of Convolution
Initialization: Start with an output signal y that has a length of len(x) + len(h) - 1.
Sliding the Kernel: For each position n in the output signal, multiply the overlapping elements of x and h, then sum these products.
Boundary Conditions: Ensure that you do not access invalid indices in either x or h during the calculation.
Example of 1D Convolution
Let's consider an example with specific values for x and h:

Input Signal: x = [1, 2, 3]
Impulse Response: h = [4, 5]
Calculation Steps:

Length of Output:
len(y) = len(x) + len(h) - 1
        = 3 + 2 - 1
        = 4
Thus, the output signal y will have a length of 4.
Compute Each Sample of Output:
For n = 0
y[0] = x[0] * h[0]
     = 1 * 4
     = 4
For n = 1:
y[2] = x[0] * h[2] + x[1] * h[1] + x[2] * h[0]
     = 1 * 0 + 2 * 5 + 3 * 4
     = 0 + 10 + 12
     = 22
For n = 2:
y[2] = x[0] * h[2] + x[1] * h[1] + x[2] * h[0]
     = 1 * 0 + 2 * 5 + 3 * 4
     = 0 + 10 + 12
     = 22
For n = 3:
y[3] = x[1] * h[2] + x[2] * h[1]
     = 2 * 0 + 3 * 5
     = 0 + 15
     = 15
Final Output:
The resulting output signal is:  y = [4, 13, 22, 15]
