# ternary_subtraction_turing_machine

## Construct a Turing machine that subtracts one ternary integer (base 3) from another. <br/>

An input will be of the form X#Y, where X and Y are elements of {0, 1, 2}+. 
<br/> 
In particular, X = xnxn-1 ... x1x0, and Y = ymym-1 ... y1y0, with each xi, yi in {0, 1, 2}, <br/> 
X = (xn x 3n) + (xn-1 x 3n-1) + ... + (x1 x 31) + (x0 x 30), and 
<br/> 
Y = (ym x 3m) + (ym-1 x 3m-1) + ... + (y1 x 31) + (y0 x 30). 
<br/>
<br/>
Your Turing machine must be a single tape, one way infinite, deterministic Turing machine. 
<br/> For this program you can use the left, right, and stay directives.
When the Turing machine completes the tape should contain Z, where Z = X - Y. You do not need to
delete X#Y from the tape, you can simply position the Turing machine read/write head at the
beginning of Z.

## Example:

122#1201 initial string
$122#1201 insert firsrt $
$$122#1201 insert second $
$$122#1201> initialize comparison to X > Y
$$12c#120b> compare 2 with 1, X > Y
$$1cc#12ab> compare 2 with 0, X > Y
$$bcc#1cab< compare 1 with 2, X < Y
$$bcc#bcab< compare 0 with 1, X < Y
$$122#1201# unmark X & Y, replace < with #
$$b22#1201#1 move 1 from X to end of tape
$$bc2#1201#12 move 2 from X to end of tape
$$bcc#1201#122 move 2 from X to end of tape
$$bcc#1201#122# X moved to end of tape, add # after it to mark where X-Y goes
$$bcc$1201#122# change the # after original X to $
$$bcc$120b#12c#2 perform subtraction 1 – 2, insert result of 2 after # need to borrow
$$bcc$112b#12c#2 after borrow
$$bcc$11cb#1cc#02 perform subtraction 2 – 2, insert result of 0 after #
$$bcc$1bcb#bcc#002 perform subtraction 1 – 1, insert result of 0 after #
$$bcc$bbcb#bcc#1002 perform subtraction 1 – 0, insert result of 1 after #
$$bcc$bbcb#bcc-1002 replace # with - infront of the result, since symbol to the left of the right most $ is not $
