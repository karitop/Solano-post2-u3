# Solano-post2-u3

C1:
| Instrucción    | AX   | BX   | CX   | IP siguiente | ZF | CF | SF |
|----------------|------|------|------|--------------|----|----|-----|
| MOV AX, 000A   | 000A | 0000 | 0000 | 0103         | NZ | NC | PL |
| MOV BX, 0005   | 000A | 0005 | 0000 | 0106         | NZ | NC | PL |
| MOV CX, 0003   | 000A | 0005 | 0003 | 0109         | NZ | NC | PL |
| ADD AX, BX     | 000F | 0005 | 0003 | 010B         | NZ | NC | PL |
| ADD AX, CX     | 0012 | 0005 | 0003 | 010D         | NZ | NC | PL |
| INT 20         | 0012 | 0005 | 0003 | 010D         | NZ | NC | PL |
