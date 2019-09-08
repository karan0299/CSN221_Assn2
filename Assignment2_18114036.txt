# Name : Karanpreet Singh
# Enrol no. : 18114036
#SubBatch : O2

#Simple RISC assembly code to find Smallest Ramanujan Number

.global _start 

_start:                    
mov r1, 0  # to store the ramanujan number
mov r0, -1 # to store the count 

loop1:
add r1,r1,1
cmp r0,2
beq exit
mov r2,0
b loop2


loop2:
add r2,r2,1
mul r4,r2,r2;     
mul r4,r4,r2; # stores the cube of one the number
mov r3,r2
cmp r4,r1
bgt loop1
b loop3

loop3:
add r3,r3,1
mul r6,r3,r3;
mul r6,r6,r3; #store the cube of second number
cmp r6,r1
bgt loop2
add r5,r4,r6 # important comparison to check if sum of cubes equals the number
cmp r5,r1
bgt ret
beq found
b loop3

found:
    add r0,r0,1 
    b loop2

#r1 is the required number

