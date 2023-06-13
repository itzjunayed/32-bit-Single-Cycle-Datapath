# Single-Cycle-Datapath
This is my CSE332(**Computer Organization and Architecture**) lab project where I have to build a 32 bit Single Cycle Datapath where its instruction is 22 bit. Here it's register file is 32 bit and it can store 32 bit wide length data in a single address of the register. 
Besides using this architecture you can do some specific operations such as: Add, Sub, XNOR, Load, Store, Branch(Beq), Set on less than, Shift Right Logic and Jump register.

## Instruction bit format
#### R-Type
OPCODE|RS|RT|RD|SHAMT
:---|:---:|:---:|:---:|---:
4 bit|5 bit|5 bit|5 bit|3 bit

#### I-Type
OPCODE|RS|RT/RD|IMMEDIATE
:---|:---:|:---:|---:
4 bit|5 bit|5 bit|8 bit

#### J-Type
OPCODE|TARGET
:---|---:
4 bit|18 bit

## ALU Operation & Control Unit Truth Table

OPCODE|INSTRUCTION|ALU OPERATION|ALUOP|REGDEST|JUMP|BRANCH|MEMREAD|MEMTOREG|MEMWRITE|ALUSRC|REGWRITE|SLT
:---|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|---:
0000|ADD|add|00|0|0|0|0|0|0|0|1|0
0001|ADDI|add|00|1|0|0|0|0|0|1|1|0
0010|SUB|sub|01|0|0|0|0|0|0|0|1|0
0011|SUBI|sub|01|1|0|0|0|0|0|1|1|0
0100|LW|add|00|1|0|0|1|1|0|1|1|0
0101|SW|add|00|x|0|0|0|x|1|1|0|0
0110|XNOR|XNOR|10|0|0|0|0|0|0|0|1|0
0111|BEQ|sub|01|x|0|1|0|x|0|0|0|0
1000|SLT|sub|01|0|0|0|0|0|0|0|1|1
1001|SRL|srl|11|0|0|0|0|0|0|0|1|0
1010|JUMP|x|xx|x|1|0|0|x|0|x|0|0


