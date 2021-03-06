# System2019

Project resources for System(II) 2019 Spring

Stay tuned

## Assignments

### PintOS

A small and simple operating system that runs on x86 machines and simulators.

### Prerequisites

- GCC with 80x86 cross-compiler
- Perl
- GNU make
- GDB
- QEMU: fast x86 simulation with binary translation, but only supports real-time mode
- Bochs: slower simulation but supports real-time and reproducible mode

To install Bochs, make sure the following library is installed:

- libncurses5-dev

Then under src/misc, run

    sudo ./bochs-2.6.2-build.sh /usr/

### Usage

First build the pintos utility tools. Under src/utils/,

    make
    export PATH=$PATH:`pwd`

The following tools are available:

- pintos: utility for running Pintos in a simulator
- pintos-gdb: launch gdb to debug the kernel
- backtrace: converting raw addresses into symbolic backtraces

In each project directory (threads, userprog, vm, filesys),

to build the project, run

    make

the following files can be found in folder 'build/'

- kernel.o: compiled kernel, used for debugging
- kernel.bin: compiled kernel, stripped
- kernel.asm: decompilation of kernel
- kernel.img: image of boot partition
- loader.bin: compiled bootloader
- loader.asm: decompilation of bootloader

to run simulation (here using Bochs and no VGA), run

    pintos -v --bochs -- -q run <testcase_name>

to debug the kernel, run

    pintos -v --bochs --gdb -- -q run <testcase_name>

in a new terminal under 'build/', run

    pintos-gdb kernel.o

in the gdb prompt, run

    debugpintos

the gdb is now connected to the kernel

to run all the tests and see your grade, run

    make grade

### Projects

#### Threads

See [JHU CS 318 Project 1](https://www.cs.jhu.edu/~huang/cs318/fall17/project/project1.html) for details.

- alarm clock
- priority scheduling
- advanced scheduler

#### User Programs

(TBD)

#### Virtual Memory

(TBD)

#### File Systems

(bonus)

#### Additional features

(bonus)

#### Design documents

You need to write design documents on your project.

Either documents on each part or documents on the project as a whole are acceptable.

Your documents shall include:

- Design for each part of the project.
- advantage & disadvantages of your design.

### Submission

For each project group:

- Place your code in a private github repository.
- Add creeperlin as collabrator and grant read permission.
- Fill up the group infromation in this [form.](https://shimo.im/sheets/FOQMFyh7ovU8SPeW)

## References

[JHU CS 318 Pintos Project](https://cs.jhu.edu/~huang/cs318/fall17/project/guide.html)

[Original JHU repository](https://github.com/jhu-cs318/pintos)

[Stanford CS 140 Pintos Project](https://web.stanford.edu/class/cs140/projects/pintos/pintos.html)

## Notes

- Get github student pack to create unlimited private repositories.
