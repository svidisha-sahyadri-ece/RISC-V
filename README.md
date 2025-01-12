# RISC-V Talent development Program

This project is based on the RISC V talent development program.
***
<details>
  <summary>Task 0-Installation</summary>
</details>
<details>
<summary>
  Task 1- Development of C Program
</summary>

### Step 1: Fire up the Terminal
```bash
vsduser@vsduser-VirtualBox:~$
```

### Step 2: Direction to home 
```bash
cd
```

### Step 3: Open leafpad
```
leafpad sum1ton.c &
```

### Step 4: Write the code
```c
#include<stdio.h>
int main() {
int i,sum=0,n=5;
for(i=1;i<=n;i++) {
sum += i;
}
printf("Sum of numbers from 1 to %d is %d",n,sum);
return 0;
}
```

### Step 5: compile and run the code
```bash
gcc sum1ton.c
./a.out
```

### Step 6: compile the program in Assembly
```bash
riscv64-unknown-elf-gcc -O1 -mabi=lp64 -march=rv64i -o sum1ton.o sum1ton.c
```

### Step 7: Disassemble  the sum1ton.o object file and enable easy scrolling
```bash
riscv64-unknown-elf-objdump -d sum1ton.o
riscv64-unknown-elf-objdump -d sum1ton.o | less
```

### Step 8: Search for the main section
```bash
/main
```

### Step 9: Compare the results with optimizations (-o1 and ofast)
```bash
riscv64-unknown-elf-gcc -O1 -mabi=lp64 -march=rv64i -o sum1ton.o sum1ton.c
riscv64-unknown-elf-gcc -Ofast -mabi=lp64 -march=rv64i -o sum1ton.o sum1ton.c
```
</details>

