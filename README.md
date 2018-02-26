Introdution

> Luckybuy draw script that was wrote by nodeJS language and using transaction hash of ethereum block as input data to draw.

> We have built a completely transparent and fully decentralized platform for organizing and conducting a lottery using the blockchain technology.
Data which using for lottery is transaction hash(es): 0x32f4f13e90df98dbaa954b509a1ab8206463565be3b9e29943459140592803c0)
This transaction hash was created when user send LKB token from user’s wallet to Luckybuy token wallet (user buy ticket to join lottery of some product).
This token was created and saved on blockchain ethereum unique and forever. No one can change and everyone can check

The processing of lottery:
1)	User buy n tickets(1 transaction hex will be created)
2)	If n > 1 then generate n-1 tickets from above(3.1.1) transaction hex by simple algorithm
3)	This hash is then broken into sequences of 4 (four) characters, starting from the tail, and transformed into a number using NHEX base 16:
32f4f13e90df98dbaa954b509a1ab8206463565be3b9e29943459140592803c0
-> 32f4 f13e 90df 98db aa95 4b50 9a1a b820 6463 565b e3b9 e299 4345 9140 5928 03c0
4)	Convert sequences of 4 (four) characters into number(base 10)
Ex: 13044 61758 37087 39131 43669 19280 39450 47136 25699 22107 58297 58009 17221 37184 22824 960
5)	Summary above number by this rule
Xn=1*13044+2*61758+3*37087+4*39131+5*43669+6*19280+7*39450+8*47136+9*25699+10*22107+11*58297+12*58009+13*17221+14*37184+15*22824+16*960
L=sum(X1->Xn)/n
6)	Find out the person who has win the lottery price
Travel all ticket. If any ticket which abs (Xn-L) has smallest value then that ticket will be winning.
If there are more than one ticket has the same smallest value then the ticket was bought prior will be win.
