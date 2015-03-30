# x86-64 #

### User Space ###

Function arguments are passed in `%rdi`, `%rsi`, `%rdx`, `%rcx`, `%r8`, `%r9`. These registers can be destroyed by the callee.

Floating point arguments are passed in `%xmm0` through `%xmm7`. These registers can be destroyed by the callee.

Additional arguments are passed on the stack

Return value in `%rax`.

| **Register** | **Use** |
|:-------------|:--------|
| `%rax` | Return value and used for varargs |
| `%rbx` | Preserved, base pointer |
| `%rcx` | Destroyed, 4th argument|
| `%rdx` | Destroyed, 3rd argument |
| `%rdi` | Destroyed, 1st argument |
| `%rsi` | Destroyed, 2nd argument |
| `%rbp` | Preserved, frame pointer |
| `%r8` | Destroyed, 5th argument |
| `%r9` | Destroyed, 6th argument |
| `%r10` | Destroyed, chain pointer |
| `%r11` | Destroyed, temporary register |
| `%r12` | Preserved |
| `%r13` | Preserved |
| `%r14` | Preserved |
| `%r15` | Preserved |

### System Calls ###

System call parameters are passed in `%rax`, `%rdi`, `%rsi`, `%rdx`, `%r10`, `%r8`, `%r9`. These registers are preserved across system calls.

Return value in `%rax`.

Aside from the parameters, the following registers are preserved: `%rbx`, `%rbp`, `%rsp`, `%r12`, `%r13`, `%r14`, `%r15`.

The kernel destroys `%rcx` and `%r11`.

| **Register** | **Use** |
|:-------------|:--------|
| `%rax` | System call number and return value |
| `%rbx` | Preserved |
| `%rcx` | Destroyed |
| `%rdx` | Preserved, 3rd argument |
| `%rdi` | Preserved, 1st argument |
| `%rsi` | Preserved, 2nd argument |
| `%rbp` | Preserved |
| `%r8` | Preserved, 5th argument |
| `%r9` | Preserved, 6th argument |
| `%r10` | Preserved, 4th argument |
| `%r11` | Destroyed |
| `%r12` | Preserved |
| `%r13` | Preserved |
| `%r14` | Preserved |
| `%r15` | Preserved |

# i386 #

### User Space ###

All parameter are passed on the stack.

Return value in `%eax`.

Commonly reserved registers are `%ebp` for the frame pointer, and `%ebx` for position independent code.

| **Register** | **Use** |
|:-------------|:--------|
| `%eax` | Return value |
| `%ebx` | Preserved, used for position independent code |
| `%ecx` | Clobbered |
| `%edx` | Clobbered |
| `%esi` | Preserved |
| `%edi` | Preserved |
| `%ebp` | Preserved, frame pointer |

### System Calls ###

System call parameters are passed in `%eax`, `%ebx`, `%ecx`, `%edx`, `%esi`, `%edi`, `%ebp`. These registers are preserved across system calls.

Return value in `%eax`.

| **Register** | **Use** |
|:-------------|:--------|
| `%eax` | System call number and return value |
| `%ebx` | Preserved, 1st argument |
| `%ecx` | Preserved, 2nd argument |
| `%edx` | Preserved, 3rd argument |
| `%esi` | Preserved, 4th argument |
| `%edi` | Preserved, 5th argument |
| `%ebp` | Preserved, 6th argument |