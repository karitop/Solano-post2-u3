# Solano-post2-u3

C1:
Programa de suma: Se ensambla un programa que carga tres valores en AX, BX y CX y los acumula en AX mediante dos instrucciones ADD. El objetivo es observar cómo cambia AX en cada paso hasta obtener el resultado final 0x0012 (18 decimal)
| Instrucción    | AX   | BX   | CX   | IP siguiente | ZF | CF | SF |
|----------------|------|------|------|--------------|----|----|-----|
| MOV AX, 000A   | 000A | 0000 | 0000 | 0103         | NZ | NC | PL |
| MOV BX, 0005   | 000A | 0005 | 0000 | 0106         | NZ | NC | PL |
| MOV CX, 0003   | 000A | 0005 | 0003 | 0109         | NZ | NC | PL |
| ADD AX, BX     | 000F | 0005 | 0003 | 010B         | NZ | NC | PL |
| ADD AX, CX     | 0012 | 0005 | 0003 | 010D         | NZ | NC | PL |
| INT 20         | 0012 | 0005 | 0003 | 010D         | NZ | NC | PL |



C2:
Programa con bucle LOOP: Se ensambla un programa que usa la instrucción LOOP para repetir una suma 4 veces. LOOP decrementa CX automáticamente y salta al inicio del bucle mientras CX != 0, acumulando 0x0002 en AX cada iteración hasta obtener 0x0008 (8 decimal)
| Iteración | Instrucción  | AX después | CX después | IP siguiente | ¿LOOP salta? |
|-----------|--------------|------------|------------|--------------|--------------|
| -         | MOV CX, 0004 | 0000       | 0004       | 0106         | -            |
| 1         | ADD AX, 0002 | 0002       | 0004       | 0109         | -            |
| 1         | LOOP 0106    | 0002       | 0003       | 0106         | Si           |
| 2         | ADD AX, 0002 | 0004       | 0003       | 0109         | -            |
| 2         | LOOP 0106    | 0004       | 0002       | 0106         | Si           |
| 3         | ADD AX, 0002 | 0006       | 0002       | 0109         | -            |
| 3         | LOOP 0106    | 0006       | 0001       | 0106         | Si           |
| 4         | ADD AX, 0002 | 0008       | 0001       | 0109         | -            |
| 4         | LOOP 0106    | 0008       | 0000       | 010B         | No           |



C3:
Análisis del código máquina: Se usa el comando D para volcar los bytes del programa en memoria y analizar cómo cada instrucción se codifica en código máquina, identificando opcodes, operandos en little-endian y desplazamientos relativos de los saltos cortos del 8086.
