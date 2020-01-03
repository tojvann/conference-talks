# Reverse Engineering the MOS 6502 CPU

## 3510 Transistors in 60 Minutes

[link](https://www.youtube.com/watch?v=fWqBmmPQP40)

- by Michael Steil

![MOS 6502](https://upload.wikimedia.org/wikipedia/commons/4/49/MOS_6502AD_4585_top.jpg)

### A brief history of MOS Technology INC

It was founded in 1974, by people who were working on 6800 at Motorola and quit the company. The Original design team of 6502 was based around Chuck Peddle who lead the team. In the year 1975 they introduced 6502 in the market. It was a very popular microprocessor used in the following machines.

- Atari 2600
- Atari 8-bit family
- Apple II
- Nintendo Entertainment System 
- Commodore 64 
- Atari Lynx 
- BBC Micro



What made 6502 microprocessor interesting as compared to the counterparts of the time. 6502 had 60% less transistors, it was much more optimized. It was not that much powerful but it was faster. It was more constrained but it was more elegant.

> It seems that perfection is attained not when there is nothing more to add, but when there is nothing more to remove
>
> -- Antoine de Saint Exupery



## Part 6502 from top down

Instead of starting from the data sheet let's simply start from the code itself.

```
STA $56 // Store Accumulator. We have 3 registers A, X and Y
JSR $BC0F // Jump to sub routine, it is a call instruction
LDA $61 //Load Accumulator
CMP #$88 //Compares the Accumulator Register
BCC $E00E //Branch if carry clear, branches if it is lower than the compared value.
JSR $BAD4 // Jump to sub routine
JSR $BCCC
LDA $07
CLC    //Clear carry flag
ADC #$81 //Add with carry
BEQ $E00B Branch equal

```



In low level programming like Assembly, it is interesting to know how encoding works. 

The opcode is always 8 bits in size i.e. it is a 1 byte opcode which encodes both the instruction and the addressing mode. The operand is either 0, 1 or 2 bytes.

Therefore there exists a 1 byte instruction like CLC since it has no operand, 2 byte instructions like STA, and 3 bytes instructions like JSR.

![](https://imgur.com/PiYHw9K.png)

*permission not obtained for using the screen-shots*



The green column in the image highlights the OPCODE and the purple column highlights the operands



### Programming model of 6502

We have got the following registers.

###### A: Accumulator

This register stores everything and transfer everything, whenever you handle data to do arithmetic and logical operations it goes through the Accumulator.



###### X, Y : Index Registers

They are used to count up and down. They can be used to as an index in accessing an array. They are not as powerful as accumulator since we cannot do any arithmetic or logical operations on the values stored in the Index Registers.



###### P: Status Register

It is a 8 bit register, Out of these 8 bits the 4 bits namely Negative, Overflow, Zero, Carry are about arithmetic and logic. One bit signals about the decimal mode. There are two more bits about exception and interrupt handling namely break and interrupt.

###### PC: Program Counter

It is a 16 bit register, since 6502 has 16 bit address space.

###### S: Stack Pointer

It is also a 16 bit register, The upper 8 bits are fixed it is hard coded to 1. So practically the Stack pointer register is only 8 bits.

![6502 Registers](https://imgur.com/Au1mnHT.png)

*permission not obtained for using the screen-shots*



## Address space

The address space of 6502 is 64 KB.

The first two pages of 256 Bytes each are special.

- The Zero Page: 0x0000 to 0x00FF

  - It is meant for all the addressing modes. If your address falls in the zero page of memory then you have special encoding and everything is faster in this 256 Bytes address space. There are somethings which can only be done in zero page address space.

- Stack: 0x0100 to 0x01FF

  - The stack is always constrained to the first page.

  - The stack counts down from 0x01FF to 0x0100

    

![Address Space 6502](https://imgur.com/EEqx9Gf.png)

 

### An ordered overview of the instruction set

![](https://imgur.com/J3nFjt4.png)

@ 7:25

