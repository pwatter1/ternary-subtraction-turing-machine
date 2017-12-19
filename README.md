# ternary_subtraction_turing_machine

Construct a Turing machine that subtracts one ternary integer (base 3) from another. <br/>
An input will be
of the form X#Y, where X and Y are elements of {0, 1, 2}+. 
<br/> 
In particular, X = xnxn-1 ... x1x0, and Y =
ymym-1 ... y1y0, with each xi, yi in {0, 1, 2}, <br/> 
X = (xn x 3n) + (xn-1 x 3n-1) + ... + (x1 x 31) + (x0 x 30), and 
<br/> 
Y = (ym x 3m) + (ym-1 x 3m-1) + ... + (y1 x 31) + (y0 x 30). 
<br/>
Your Turing machine must be a single tape, one way infinite, deterministic Turing machine. 
<br/> For this program you can use the left, right, and stay directives.
When the Turing machine completes the tape should contain Z, where Z = X - Y. You do not need to
delete X#Y from the tape, you can simply position the Turing machine read/write head at the
beginning of Z.
