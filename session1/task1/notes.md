Python stops exactly when the invalid index is used and gives a very clear traceback:
it shows:
1.the file
2. the line number
3. the statement causing the error
4. the type of error: IndexError
5.the reason: list assignment index out of range
Python clearly says that the program tried to write outside the list.

C on the other hand.
The program did not immediately stop at the bad array access and it even printed Done!
Only afterwards did the system detect memory corruption
The message is much more low-level and less specific than Python’s traceback
Stack smashing detected means the program wrote beyond the bounds of local stack memory and damaged something important.

The Python program would be easier to debug because its traceback clearly explains both what went wrong and where it happened. The C program only reports stack corruption after the invalid memory write, so its observed behaviour is less specific and harder to trace back to the exact source of the bug.