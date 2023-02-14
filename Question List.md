- [ ] Why analyzing the forward propagation of errors is often difficult? (book p.11)

- [ ] Is forward error truncation error? (lecture1 p.5)

- [ ] What is the trade of between stable and accuracy? (lecture1 p.10)

- [ ] roundoff error is rounding error? "The condition number tells use the worst-case amplification of output error with respect to input error"? (lecture1 p.11)

- [x] $fl(x)$ is a "binary form" of scientific notation (how could we have number 2 in binary form, also the exponent)? Mantissa is bunch of 0 and 1?  (lecture1 p.12)

- [ ] How to understand the machine epsilon? (lecture1 p.13)

  - [x]  $|\frac{fl(x) - x}{x}| \leq \epsilon_{mach}$ (from book). 
  - [x] "If we have s significant digits in scientific notation, our error is bounded to ==variations of 1== in least significant digit (the last digit? yes), whose magnitude relative to the number we are trying to represent is $10^{1-s}$ in decimal and $2^{1-s}$ in binary."
  - [ ] How to understand the formula at the second bullet? Is $x_{rem}$ rouding error?

- [ ] Rounding error in operations:(lecture1 p.14)

  - [ ] Why adding large number with small number cause high rounding error? (lecture notes)

  - [ ] Catastrophic cancellation demo?

  - [ ] Absolute error of addition: $fl(fl(x) + fl(y))$ is $[x(1+\epsilon) + y(1+\epsilon)](1+\epsilon) - (x + y)$? Where does $1 + \epsilon $ come from?

  - [ ] Relative error of addition:
    $$
    \frac{fl(fl(x) + fl(y)) - (x+y)}{|x+y|} \leq \frac{fl(x) + fl(y) - (x+y)}{|x+y|} + \epsilon \\
     \frac{fl(x) + fl(y) - (x+y)}{|x+y|} + \epsilon \leq \frac{[fl(x) - x] + [fl(y) - y]}{|x+y|} + \epsilon
    $$

- [ ] Normalization: 
  - [x] Why the gap between two fl(x) is increading? And why in subnormal it's even? (lecture 1 p.17)
  - [ ] Why subnormal system cannot guarantee the uniqueness? (quiz 1 p.6)
  - [ ] Normal system could minimize rounding error because it could spare extra one bit of precision? (quiz p.6)
  - [ ] Why +-$2^L$ is the bound of normal floating system? (book p.21)