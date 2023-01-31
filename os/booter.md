# BOOTER

## How to develop a BOOTER

sdimage is used by ARM like a SD card

Separated by sector
Get 2 block to find the files shows where inode beginning block is
Read block by block

sdc is a driver that works with ARM provides two functions

1. Get block into memory
Block 2 has root contains . and ..
step through until you find boot find inumber and convert to inode
/boot/kernel
kernel files are inside the boot
Read 1mb because KC designed his kernel to run with 1mb
find the os kernel
load into memory according to specifications
put at start of memory and job is done

RISC machine - reduced instructions set computer

## Boot Lab

* sdimage contains the /boot folder which needs to be read in
* need to implement printf in order to print to console (started but make more complex)
* transfer control to 1meg

## Timer

* interrupt driven output device
* counts the tics and advances the seconds after __ tics
* after 60 seconds changes the minute

## Notes

* unix/linux P1 is called init process
* ps command prints the process statuses
* every other process is generated by P1

P1 is the becomes the temporary parent of any zombie children, P1 job is to just loop and wait for a zombie and then free it properly (free and report how it died).

kill -9 signal that no process can ignore

it is possible for a process to get stuck and ignore every signal that is sent to it.

## Files
* t.ld file loads into memory the areas for storage, data and allocates space for the stack setting the stack top
* ts.s file loads the stack pointer into register
* uart.c file to define uprintf functions and import and define as printf 

Get char out char then printf

sdc.c
Intended to get sector and get block from disk
Initialize sd card

boot.c
Defined boot process in here. 
I put booter, real work done here
Load into memory, when done return to main.

### Submission
Submit lab using email
Compress file
Make it so it can just be run with mk
Test one command in the OS
You can assume only one data block

iblock zero
Step 3
Strncpy to make string and then end with null
This is to make strcmp work
Step 8 
Loop should be after setting address

‘*’ is due direct blocks loaded
‘•’ is indirect 

Chapter 3 is about booter