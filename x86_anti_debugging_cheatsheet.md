
```assembly
; Anti-Debugging Techniques

; Check for Debugger Presence
int3                ; Trigger a breakpoint interrupt (INT 3)
                  ; In a debugger, this will pause execution
                  ; Detectable by a debugger by monitoring INT 3
                  ; Often used to detect software breakpoints

; Check for Debug Registers
mov eax, dr0         ; Load the value of debug register DR0
mov eax, dr1         ; Load the value of debug register DR1
mov eax, dr2         ; Load the value of debug register DR2
mov eax, dr3         ; Load the value of debug register DR3
                  ; Debug registers are used for hardware breakpoints
                  ; If they contain non-zero values, it may indicate debugging

; Check for Debugging Flags
pushfd              ; Push the EFLAGS register onto the stack
pop eax             ; Pop EFLAGS into eax
and eax, 0x100       ; Test the TF (Trap Flag) bit in EFLAGS
                  ; TF is set when single-stepping in a debugger
                  ; Presence of TF may indicate debugging

; Check for Being Debugged by IsDebuggerPresent API
push 0               ; Load a value of 0 onto the stack (return value)
call IsDebuggerPresent
test eax, eax        ; Check if the return value is non-zero (debugger present)

; Detect Debugger Using Timing
rdtsc               ; Read the time-stamp counter (TSC)
                  ; The timing difference between consecutive rdtsc
                  ; instructions can be used to detect debugger presence

; Detect Virtual Machine (VM) or Hypervisor
cpuid               ; Execute the CPUID instruction
                  ; Check the output for known VM or hypervisor vendor IDs
                  ; VMs often return specific values

; Interrupt 0x2D
int 0x2D            ; Execute INT 0x2D (Software breakpoint)
                  ; Some debuggers hook this interrupt for their own use
                  ; Detecting this can indicate the presence of a debugger

; Timing Checks
; Measure the time taken for certain operations
; Compare it with expected values to detect debugging (e.g., time-based anti-debugging)

```