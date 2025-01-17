# Assembly Language Tutorial

## Compile and run 
```
global _start

section .text

_start:
    ; print hello world
    mov rax, 1  ; write syscall
    mov rdi, 1  ;fd -> 1 (output)
    mov rsi, hello ;buffer -> hello -> 'hello world'
    mov rdx, 11  ;count -> 11 (size)
    syscall

    mov rax, 60 ;exit syscall
    mov rdi, 11 ; status code -> 22
    syscall

section .data

    hello: db 'hello world'
```

##  Assemble the Code
```
nasm -f elf64 hello.asm -o hello.o
```

## Link the Object File
```
ld hello.o -o hello
```
## Run
```
./hello
```











