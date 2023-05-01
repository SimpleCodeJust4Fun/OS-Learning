# chick and rabbit problem using RISC-V simulation cpu

cpu fetch instruction and execute in while loop

six instruction implemented total 
```
    #define __ else if // Bad syntactic sugar!
    if (op == 0b0110011 && f3 == 0b000 && f7 == 0b0000000) res = rs1_u + rs2_u;
    __ (op == 0b0110011 && f3 == 0b000 && f7 == 0b0100000) res = rs1_u - rs2_u;
    __ (op == 0b0010011 && f3 == 0b000)                    res = rs1_u + imm;
    __ (op == 0b0010011 && f3 == 0b001 && f7 == 0b0000000) res = rs1_u << shamt;
    __ (op == 0b0010011 && f3 == 0b101 && f7 == 0b0000000) res = rs1_u >> shamt;
    __ (op == 0b1110011 && f3 == 0b000 && rd == 0 && imm == 1) ebreak(&cpu);
```

the instructions are stored in ji-tu.txt (this file can be viewed as memory) and loaded through pipe in Makefile:
```
run: a.out
	@echo 2 Head, 4 Feet:
	@cat ji-tu.txt | ./a.out 2 4
	@echo 2 Head, 6 Feet:
	@cat ji-tu.txt | ./a.out 2 6
	@echo 2 Head, 8 Feet:
	@cat ji-tu.txt | ./a.out 2 8
	@echo 35 Head, 94 Feet:
	@cat ji-tu.txt | ./a.out 35 94
```
