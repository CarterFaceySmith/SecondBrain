How do [[CPU]]s run them? Good question.

1. **Load**: A compiled executable file is loaded into [[RAM]] [[Memory]].
2. **Fetch**: The CPU reads the first address register in RAM and it is sent to the instruction register of the CPU.
3. **Interpret**: The CPU control unit reads and interprets the instruction.
4. **Execute**: The control unit sets the information up so that the instruction can be executed, i.e loading data into information registers etc. The program counter is then incremented.
5. Runs until the `HALT` [[Assembly]] instruction is reached.

Example: `ADD R0 R1` ([[Assembly]]) and `STR R0 0111` (Also [[Assembly]])

We can also use the `JUMP` instruction, which in reality just overrides the CPU instruction address register with the jump address, loading the next instruction from there. These loops are bounded using a combo of conditonal and non-conditional jumps normally.



See also:
- [How computer processors run conditions and loops](https://www.youtube.com/watch?v=Ui6QyzcD3_E)