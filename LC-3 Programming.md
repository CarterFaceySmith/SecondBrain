# LC-3 Programming

Welcome to coding in assembly bby.

		; LC−3 Program that displays  
		; ” Hello World !” to the console  
		.ORIG x3000  
		LEA R0 , HW ; load address of string  
		PUTS ; output string to console  
		HALT ; end program  
		HW .STRINGZ ” Hello World ! ”  
		.END

The above is an LC-3 program for outputting "Hello World!" to the console.

**.ORIG** is a 'pseudo op', an equivalent to a preprocessing directive that helps the compiler do its job, this one directs the assembler where to place the code in memory. All LC-3 programs begin this way.

Memory in LC-3 holds either data or instructions that manipulate data. Convention is to commence at position x3000 as above, the code will then continue from there placing each statement into the following memory location (x3001, x3002....etc).

HALT is important, it signifies the end of the prog.
Of note, .END signifies the end of the code entirely, the lines between it and HALT are for data you would like to manipulate in the prog itself, in this case the string. .END is always the last line.

#### Dissecting an LC-3 instruction cos who understands this shit naturally

Let's take this line here:

		LEA R0 , HW ; load address of string
		
1. Label: This line doesnt have one, the 'HW' in the above prog is one though, it's used to reference the data in the prog like in the above line
2. Opcode: This is the instruction type, LEA above. Mandatory for each line.
3. Operand: Required by most instructions, R0 above. Indicates what data is being manipulated.
4. Comment: Optional, you know what this is, it's seperated by a semicolon from the main instruc.


#### Two's Complement

To turn an integer into it's negative in binary, we:
- invert the digits
- then add one to the result
- eg. 00011100 -> 11100011 -> 11100100


See also:
- [[Assembly, Registers, and the Stack Model]]
- [[LC-3 Memory]]
- [[TRAPs]]