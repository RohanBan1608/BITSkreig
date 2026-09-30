## Challenge Name = transformation

## Approach
I did not understand what the chr(), ord() and what the << ,>> did in python. After reading up on these functions, and about the 8 bit operations, left shifting and right shifting, I concluded that the code took the flag, and for every character in the flag, it left shifted the i'th character by 8, i.e. multiplying the ASCII value by 256, and added the ASCII value of the next character(flag[i+1]) to it, and did this for all pairs of characters. So, if a character has ASCII value = 65, 
it would multiply it by 65*256, and add the next character's ASCII value to it. So, I thought that in order to get the decoded flag, I would take each character, and divide it by 256, to get flag[i]. Then, I would take the remainder by % 256, and get the second character, and join these characters together, for all i. That gave me the solution

## Solution:
My working code:
c = "慣慤敭祻ㄶ形楴獟楮獴㌴摟潦弸強㤰扡㌷敽"

flag = "".join((chr(ord(ch) >> 8) + chr(ord(ch)%256)) for ch in c)
print(flag)

![python code](screenshots/simage.png)


## Flag: academy{16_bits_inst34d_of_8_790ba37e}

## Takeaway:
I learnt about left shifting and right shifting bits, and what that practically means, and how to use that in code.
