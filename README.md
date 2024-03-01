# Notes
Daily update about classes

DATE:14/02/2024


RAM is a primary storage memory which is volatile.
Secondary memory is non volatile.
RAM's are Dynamic Random Access Memory(DRAM) and Static Random Access Memory (SRAM).
Static RAM (SRaM) is faster than Dynamic RAM (DRAM).
Dynamic RAM (DRAM) are made up of transistor and capacitor.
Static RAM (SRAM) is made up of several transistors that form a latch.
GPIO (General purpose Input/Output)is a peripheral that allows communication with the outside environment.
The system bus is the median that connects peripherals to the processor.It has eight buses.
CPU(Central processing Unit) contain ALU(Arithmetic Logic Unit).
CPU performs ALU operations that is Arithmetic operations and logic operation .
The clock speed is 180 MHZ.
Cortex M is a microprocessor that contains only the processor.
ARM Cortex M4 it cotains an I-Bus,D-Bus and S-Bus.
I-Bus -Instrection Bus.
D-Bus -Data Bus.
S-Bus -System Bus.
Peripherals are sending by using "SYSTEM BUS"(S-Bus).
GPIO's it has GPIO PIN and GPIO PORT.
Many GPIO PIN join together is called Port.
If enable line is 1 output buffer will work..If enable line is 0 input buffer will work.
High Z state - we couldn't predict ,it is high or low (floating state)
We want to give PULL UP or PULL DOWN during input,resistor to connect ,it will give STABLE.
GPIO OUTPUT MODE:  1)open drain state.2)pull up configuration. 3)when the transitor is ON,the pin is pulled to ground.
To access the GPIOA port ,we have to activate the clock.
MODER(COnfigure the I/O direction mode): 1) 0 0 input (reset state). 2) 0 1 General purpose output mode. 3) 1 0 Alternate function mode. 4) 1 1 Analog mode.

DATE:15/02/2024


PHERIPHERALS: 1)GPIO 2)I2C 3)SPI 4)Timer.
GPIO -have 7 memory space and address ,that memory space is called REGISTERS.
GPIO A to GPIO H having different memory space and having same registers.
REGISTERS: 1) MODER 2) OTYPER 3) OSPEEDR 4) PUPDR 5) IDR 6) ODR 7)BSRR 8) LCKR 9) AFRL.
GPIO A base address will be 0*40020000.
we know the base address of GPIO and we know thw offset of GPIO.
Physical address has 8 bit or byte addressable.Base address is 20 and offset is 20 --Address will be start at 40 (20+20=40).

DATE: 16/02/2024

__IO -> volatile GPIO typedefGPIO_BASE here GPIO typedef is one structure for different address GPIOA BASE, GPIOB BASE,..... AHB1ENR , The registers above the ABH1ENR should be used for that we will create a dummy , The registers below the ABH1ENR is no need to use. DELAY -> used to blink RR_TYPEDEF -> using structure you cahnge all the values to address.

GPIO_BASE (AHB1PERIPH_BASE + GPIO_OFFSET) When we use the (volatile unsigned int )then we call as address integer poiter typecaste (RCC_BASE + AHB1EN_R_OFFSET)will be changes as address. ((volatile unsigned int *)(RCC_BASE + AHB1EN_R_OFFSET))

DATE:21/02/2024


1)Serial communication:8-bit data is transfered one bit at a time and line by line process(one by one bit).

2)Parallel Communication:8-bit data is transfered the same time(full data send at a time).

Serial data communication uses two methods: 

       1)Synchronous-clock is transmitted with the data.

       2)Asynchronous-no clock is tramitted.Transmitter and Receiver agree on the clock speed for the data transmission(Baudrate).

UART-Universal Synchronous Receiver/Transmitter and UART is a serial communication protocol.

USART-Universal Asynchronous Receiver/Transmitter.

1)Duplex:Data can be transmitted and received.(eg:Mobile Phones).2)Simplex:Data can be transmitted only or received only. ie)one direction only(eg:Radio).
3)Half Duplex:Data can be transmitted in only one way at a time.(eg:Walky Talky).4)Full Duplex:Data can be transmitted in both ways.(eg:UART).

DATE:22/02/2024

sudo apt get install minicom for linux everything is a file or it is a process,in linux mouse, keyboard are file

in new tab ls / ls /dev ls -l /dev

SOC-system on chip ---->Name in soc SOM-system on module------>phycore A5D2X SBC-single board computer----->rugged board A5D2X

Three types of boot

    flash memory boot
    sd card booot
    network boot flash memory is like a harddisk

at91.bootstrap ---->primary

boot RDm-->it works as load to the SRAM u-boot--> it will load in .dtb RAM .dts--->device tree source .dtsi---->device tree source include .dtb--->compiles both .dts and .dtsi FInally load all and only mount thr RFS


DATE:28/02/2024

ARM

electronic Gadgets

ARM

Before ARM introduce we have CICS

Cles ARM

load and store These & instructions only work in memory other instructions all work in Registers.

Soume file

• C

.i

•S assembly

elf
Secondary memory saves the saved codes.. when the code is send from secondary memory to primary
=> For one set architecture neraiya microarchitecture inukum.

Arm is not a chip manufacturing company" design



Family can have multiple architecture for that can have multiple procusor.
ARM architecture specifier

at con how

Multiple procellor

Instruction set


Register set

interrupt



Exception model



Memory model



Debug, Trace and profilines

fioud point

RISC- Reduced instruction set computer



simple instructions



simple Addressing modes


Load store Architecture


Big Endian and little Endian

Mioro architecture

build and design of a processor

Number and sizes of cache

cycle court for individual instructions

which optional feature are implemented
Notes GitHub update pannikonga
ARM Dowmentation

- ARM [architecture reference manual]

- TRM [ Technical reference manual]

-

CIM [Configuration and integration manual] Soc datasheet.


DATE:29/2/24

SHELL SCRIPT shell- is a program A shell script is a textfile containing a series of commands that are interpreted and executed by a shell program. shell scripts are used to automate tasks, execute commands or perform various oprations within the linux environment.

mkdir folder name vim filename.sh #!/bin/bash echo "Rathinam Technical Campus" exit 0 chmod 777 filename.sh ./filename.sh

Library--->system call--->kernel it will acess the kernel PROCESS CREATION system()-->Library function fork()-->system call wait()-->system call ----->its all call the clone for execution waitpid()-->system call exec()-->system call clone()-->clone system call

wait and waitpid is used avoid zombie process. to see the content inside folder we use "ls -al" By using System library we can run the bash command. there are 9 man pages available.

Fork creates a new process then the new process is referred to us child process, the calling is called the parent process, both child and parent process have separate memory.
