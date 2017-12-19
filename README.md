# ternary_subtraction_turing_machine

## Construct a Turing machine that subtracts one ternary integer (base 3) from another. <br/>

An input will be of the form X#Y, where X and Y are elements of {0, 1, 2}+. 
<br/>
Your Turing machine must be a single tape, one way infinite, deterministic Turing machine. 
<br/> For this program you can use the left, right, and stay directives.
When the Turing machine completes the tape should contain Z, where Z = X - Y. You do not need to
delete X#Y from the tape, you can simply position the Turing machine read/write head at the
beginning of Z.

## Example:

122#1201 initial string <br/>
$122#1201 insert firsrt $ <br/>
$$122#1201 insert second $ <br/>
$$122#1201> initialize comparison to X > Y <br/>
$$12c#120b> compare 2 with 1, X > Y <br/>
$$1cc#12ab> compare 2 with 0, X > Y <br/>
$$bcc#1cab< compare 1 with 2, X < Y <br/>
$$bcc#bcab< compare 0 with 1, X < Y <br/>
$$122#1201# unmark X & Y, replace < with # <br/>
$$b22#1201#1 move 1 from X to end of tape <br/>
$$bc2#1201#12 move 2 from X to end of tape <br/>
$$bcc#1201#122 move 2 from X to end of tape <br/>
$$bcc#1201#122# X moved to end of tape, add # after it to mark where X-Y goes <br/>
$$bcc$1201#122# change the # after original X to $ <br/>
$$bcc$120b#12c#2 perform subtraction 1 – 2, insert result of 2 after # need to borrow <br/>
$$bcc$112b#12c#2 after borrow <br/>
$$bcc$11cb#1cc#02 perform subtraction 2 – 2, insert result of 0 after # <br/>
$$bcc$1bcb#bcc#002 perform subtraction 1 – 1, insert result of 0 after # <br/>
$$bcc$bbcb#bcc#1002 perform subtraction 1 – 0, insert result of 1 after # <br/>
$$bcc$bbcb#bcc-1002 replace # with - infront of the result, since symbol to the left of the right most $ is not $ <br/>
