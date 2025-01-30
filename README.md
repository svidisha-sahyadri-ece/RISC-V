# RISC-V Talent development Program

## About Me
Name: S VIDISHA

College: Sahyadri College Of Engineering and Management

Email ID: vidisha.ec23@sahyadri.edu.in

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
int i,sum=0,n=100;
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
![./a.out](https://github.com/svidisha-sahyadri-ece/RISC-V/blob/a9a64d642f8114aba339ff1b65eff1dd96f5016b/riscv%20task1/riscv%20task1(sum1ton).png?raw=true)

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
![o1](https://github.com/svidisha-sahyadri-ece/RISC-V/blob/25a3f2c6fefe88f40845cd8ead96d9261242dad4/riscv%20task1/riscv%20task1(o1).png?raw=true)
![ofast](https://github.com/svidisha-sahyadri-ece/RISC-V/blob/4da56089c29554c787638785a601053e4bcdb792/riscv%20task1/riscv%20task1(ofast).png?raw=true)
</details>
<details>
<summary> Task 2- Simulation with spike</summary>
<hr> 
Test Spike by running a sample program (e.g. factorial.c) using both gcc compiler and RISC-V compiler and confirm that both the compilers generates same output

### Step 1: Compile and run the program in riscv using spike
```bash
spike pk factorial.o
```
![spike pk factorial.o](https://github.com/svidisha-sahyadri-ece/RISC-V/blob/71885a4a4432fa4460bd5cad79bfebe032704a57/riscv%20task2/riscv%20task2%20spike.png?raw=true)

### Step 2: Compile with the optimization level Ofast
```bash
riscv64-unknown-elf-gcc -Ofast -mabi=lp64 -march=rv64i -o factorial.o factorial.c
```
![ofast](https://github.com/svidisha-sahyadri-ece/RISC-V/blob/c10220a6e5c3860fa788bd6f9c167d3caa478bd6/riscv%20task2/riscv%20task2(ofast).png?raw=true)

### Step 3: Generate an object dump
```bash
riscv64-unknown-elf-objdump -d factorial.o | less
```

### Step 4: Run the program with Spike debugger
```bash
spike -d pk factorial.o
```
![spike debug](https://github.com/svidisha-sahyadri-ece/RISC-V/blob/32002c59a82fd30363c7afccc572cbbbb0aa2b0f/riscv%20task2/riscv%20task2%20spike(debug).png?raw=true)


  
</details>

<details>
<summary> Task 3- RISC-V Instructions and their Encodings</summary>

## 15 Unique RISC-V Instructions and thier 32- Bit encodings:

## RISC-V instructions and thier Encodings

**auipc a5,0xffff0**
- Type: U-Type
- Binary Encoding: 11111111111111110000011110010111

**addi a5,a5,-176**
- Type: I-Type
- Binary Encoding: 11110101000001111000011110010011

**beqz a5,100c8**
- Type: B-Type
- Binary Encoding: 00000000000001111000100001100011

**auipc a0,0x0**
- Type: U-Type
- Binary Encoding: 00000000000000000000010100010111

**addi a0,a0,424**
- Type: I-Type
- Binary Encoding: 00010100100001010000010100010011

**j 1021c**
- Type: J-Type
- Binary Encoding: 00010101100000000000000001101111

**ret**
- Type: I-Type
- Binary Encoding: 00000000000000001000000001100111

**auipc gp,0x13**
- Type: U-Type
- Binary Encoding: 00000000000000010011000110010111

**addi gp,gp,-1732**
- Type: I-Type
- Binary Encoding: 10010011110000011000000110010011

**addi a0,gp,1904**
- Type: I-Type
- Binary Encoding: 01110111000000011000010100010011

**auipc a2,0x13**
- Type: U-Type
- Binary Encoding: 00000000000000010011011000010111

**addi a2,a2,304**
- Type: I-Type
- Binary Encoding: 00010011000001100000011000010011

**sub a2,a2,a0**
- Type: R-Type
- Binary Encoding: 01000000001001100000011000110011

**li a1,0**
- Type: I-Type
- Binary Encoding: 00000000000000000000010110010011

**jal ra,10354**
- Type: J-Type
- Binary Encoding: 00100110110000000000000011101111


</details>
<details>
  <summary>Task 4 - Functional Simulation of RISC-V Core</summary>
  
  ### Step 1: Create a directory

  ### Step 2: Create the verilog files using touch command

  ### Step 3: locate the Files created and paste the code from <a href="https://github.com/vinayrayapati/rv32i/blob/main/?> repo</a>
  Get the Verilog netlist from <a href="https://github.com/vinayrayapati/rv32i/blob/main/iiitb_rv32i.v">RISC-V Core Verilog Netlist.</a>
  Get the testbench from<a href="https://github.com/vinayrayapati/rv32i/blob/main/iiitb_rv32i_tb.v">Testbench for RISC-V Core.

  ### Step 4: Compile the Files

  ### Step 5: Run the Files

  ### Step 6: Open the Files in GTKWave 

  ### Step 7: Add signals to GTKWave
</details>

<details>
  <summary> Task 5 - Project Overview</summary>

  ## RISC-V Based Temperature and Humidity Monitor

  A simple project using RISC-V board to measure and display temperature and humidity using a DHT11 sensor and an OLED display.

  ## Features

  - Real-time temperature and Humidity display
  - Low power consumption
  - can be expanded for IOT applications

### Components Required

- RISC-V Board (e.g., sipeed Longan Nano / HiFive1)
- DHT11 Temperature and Humidity Sensor (SSD1306, I2C)
- 0.96 OLED Display 
- Jumper Wires
- 5V Power Supply (USB or Battery)

### Circuit 

![](https://github.com/svidisha-sahyadri-ece/RISC-V/blob/dedc2febbef1254da9d903c538b8ba25f91c6495/riscv%20task5/Temperature%20and%20Humidity%20Monitor.png?raw=true)

## Pin Details

| Component | Pin on RISC-V  Board | Pin on component | Description |
|----------|-----------------------|------------------|--------------|
| DHT11 Sensor | 3.3V | VCC | Power |
|              | GND | GND | Ground |
|              | PC0 | Data | Data Signal |
| OLED Display | 3.3V | VCC | Power |
|               | GND | GND | Ground |
|               | PC4 | SDA | I2C Data|
|               | PC5 | SCL | I2C Clock |



  


  
</details>

