
```assembly
; x86 Assembly Language Cheat Sheet

; Data Movement Instructions
mov dest, src       ; Move data from src to dest
push value          ; Push a value onto the stack
pop dest            ; Pop a value from the stack into dest

; Arithmetic Instructions
add dest, src       ; Add src to dest
sub dest, src       ; Subtract src from dest
mul src             ; Multiply EAX by src (signed)
imul src            ; Multiply EAX by src (signed, result in EDX:EAX)
div src             ; Divide EDX:EAX by src (signed)
idiv src            ; Divide EDX:EAX by src (signed, result in EDX:EAX)

; Logic Instructions
and dest, src       ; Bitwise AND src with dest
or dest, src        ; Bitwise OR src with dest
xor dest, src       ; Bitwise XOR src with dest
not dest            ; Bitwise NOT dest
shl dest, count     ; Shift dest left by count bits
shr dest, count     ; Shift dest right by count bits
sar dest, count     ; Arithmetic shift right (sign-preserving)

; Conditional Jumps (based on flags)
je label            ; Jump if Equal (ZF = 1)
jne label           ; Jump if Not Equal (ZF = 0)
jz label            ; Jump if Zero (ZF = 1)
jnz label           ; Jump if Not Zero (ZF = 0)
jb/jnae label      ; Jump if Below/Carry (CF = 1)
jnb/jae label      ; Jump if Not Below/Carry (CF = 0)
jbe/jna label      ; Jump if Below or Equal (CF = 1 or ZF = 1)
jae/jnbe label     ; Jump if Above or Equal (CF = 0 and ZF = 0)
js label            ; Jump if Sign (SF = 1)
jns label           ; Jump if Not Sign (SF = 0)
jo label            ; Jump if Overflow (OF = 1)
jno label           ; Jump if No Overflow (OF = 0)

; Unconditional Jumps
jmp label           ; Jump unconditionally
call label          ; Call a subroutine at label
ret                 ; Return from subroutine

; Compare Instructions
cmp dest, src       ; Compare dest and src (sets flags, no result stored)
test dest, src      ; Bitwise AND dest and src (sets flags, no result stored)

; Data Types
db  value            ; Define a byte
dw  value            ; Define a word (2 bytes)
dd  value            ; Define a doubleword (4 bytes)
dq  value            ; Define a quadword (8 bytes)

; Stack Operations
pusha               ; Push all general-purpose registers onto the stack
popa                ; Pop all general-purpose registers from the stack
pushad              ; Push all 32-bit general-purpose registers onto the stack
popad               ; Pop all 32-bit general-purpose registers from the stack
pushf               ; Push the flags register onto the stack
popf                ; Pop the flags register from the stack

; Miscellaneous Instructions
nop                 ; No operation (do nothing)
hlt                 ; Halt the CPU
int n               ; Generate a software interrupt with interrupt number n
```
