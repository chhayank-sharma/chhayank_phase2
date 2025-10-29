# 1. GDB baby step 1

## Description:

Can you figure out what is in the eax register at the end of the main function? Put your answer in the picoCTF flag format: picoCTF{n} where n is the contents of the eax register in the decimal number base. If the answer was 0x11 your flag would be picoCTF{17}. Disassemble [this](RE/debugger0_a).

## Solution:
 
In this challenge, we have been given an executable `debugger0_a`. We have to disassemble it and determine the value that is being stored in the eax register. Then, we must convert the obtained hex value to decimal and put it between `picoCTF{` and `}` to get the flag.

We must open the binary in gdb. Then, we can run `disassemble main` to get the dissasembled output. Here, we can observe that the value `0x86342` is being stored into the `eax` register.

On converting the hex value to decimal, we get `549698`. Thus, our flag is `picoCTF{549698}`.

### Commands Run:
```sh
$ gdb -q debugger0_a
Reading symbols from debugger0_a...

This GDB supports auto-downloading debuginfo from the following URLs:
  <https://debuginfod.fedoraproject.org/>
Enable debuginfod for this session? (y or [n]) n
Debuginfod has been disabled.
To make this setting permanent, add 'set debuginfod enabled off' to .gdbinit.
(No debugging symbols found in debugger0_a)
(gdb) disassemble main
Dump of assembler code for function main:
   0x0000000000001129 <+0>:     endbr64
   0x000000000000112d <+4>:     push   %rbp
   0x000000000000112e <+5>:     mov    %rsp,%rbp
   0x0000000000001131 <+8>:     mov    %edi,-0x4(%rbp)
   0x0000000000001134 <+11>:    mov    %rsi,-0x10(%rbp)
   0x0000000000001138 <+15>:    mov    $0x86342,%eax
   0x000000000000113d <+20>:    pop    %rbp
   0x000000000000113e <+21>:    ret
End of assembler dump.
```

## Flag:

```
picoCTF{549698}
```

## Concepts learnt:

- How to use gdb to open and disassemble a binary

***

# 2. ARMssembly 1

For what argument does this program print `win` with variables 81, 0 and 3? File: [chall_1.S](RE/chall_1.S) Flag format: picoCTF{XXXXXXXX} -> (hex, lowercase, no 0x, and 32 bits. ex. 5614267 would be picoCTF{0055aabb})

## Solution:

In this challenge, we have been given a file containing arm assembly. To solve this challenge, we need to understand what the code does and figure out what the input must be to get it to print win. Then, we must convert the required input value to hex and put it between `picoCTF{` and `}` without the `0x` at the beginning to get the flag.

<details closed>
<summary><i>Assembly code</i></summary>

```as
 1          .arch armv8-a
 2          .file   "chall_1.c"
 3          .text
 4          .align  2
 5          .global func
 6          .type   func, %function
 7  func:
 8          sub     sp, sp, #32
 9          str     w0, [sp, 12]
10          mov     w0, 81
11          str     w0, [sp, 16]
12          str     wzr, [sp, 20]
13          mov     w0, 3
14          str     w0, [sp, 24]
15          ldr     w0, [sp, 20]
16          ldr     w1, [sp, 16]
17          lsl     w0, w1, w0
18          str     w0, [sp, 28]
19          ldr     w1, [sp, 28]
20          ldr     w0, [sp, 24]
21          sdiv    w0, w1, w0
22          str     w0, [sp, 28]
23          ldr     w1, [sp, 28]
24          ldr     w0, [sp, 12]
25          sub     w0, w1, w0
26          str     w0, [sp, 28]
27          ldr     w0, [sp, 28]
28          add     sp, sp, 32
29          ret
30          .size   func, .-func
31          .section        .rodata
32          .align  3
33  .LC0:
34          .string "You win!"
35          .align  3
36  .LC1:
37          .string "You Lose :("
38          .text
39          .align  2
40          .global main
41          .type   main, %function
42  main:
43          stp     x29, x30, [sp, -48]!
44          add     x29, sp, 0
45          str     w0, [x29, 28]
46          str     x1, [x29, 16]
47          ldr     x0, [x29, 16]
48          add     x0, x0, 8
49          ldr     x0, [x0]
50          bl      atoi
51          str     w0, [x29, 44]
52          ldr     w0, [x29, 44]
53          bl      func
54          cmp     w0, 0
55          bne     .L4
56          adrp    x0, .LC0
57          add     x0, x0, :lo12:.LC0
58          bl      puts
59          b       .L6
60  .L4:
61          adrp    x0, .LC1
62          add     x0, x0, :lo12:.LC1
63          bl      puts
64  .L6:
65          nop
66          ldp     x29, x30, [sp], 48
67          ret
68          .size   main, .-main
69          .ident  "GCC: (Ubuntu/Linaro 7.5.0-3ubuntu1~18.04) 7.5.0"
70          .section        .note.GNU-stack,"",@progbits
```

</details>

We should start analysing the assembly from the main function. We can see what each bit of assembly does line by line:

```
43: This line actually does two things. It first subtracts 48 from the stack pointer. i.e., it allocates 48 bytes in the memory in the stack for local variables. Then, it stores two important registers into that memory: the frame pointer(x29), is used to store the base address of the stack and provides a fixed reference to access the memory), and the return address(x30).

44: This line makes x29 point to the current value of sp. i.e., it stores the current stack pointer location into the frame pointer, setting that as reference.

45: It stores argc(w0) into the stack at an offset of 28 more than the current frame pointer location.

46: It stores the position of argv(x1) into the stack at an offset of 16 more than the current frame pointer location.

47: It loads [x29, 16] into x0. i.e., it it loads the position of argv(x1) into x0.

48: It add 8 bytes to x0 so now it points to argv[1]. i.e. it now points to the first argument after the program name.

49: It dereferences x0 to make x0 point to the string stored at argv[1] rather than the argv[1] array entry.

50: Calls the function atoi which converts the string passed as argv[1] into an integer and stores it into w0.

51: Stores w0 into the stack slot at [x29 , 44].

52: Loads that integer just stored at [x29, 44] back into w0.

53: Calls func with the vaue in w0 and store its return value in w0

54: Compares if w0 is equal to 0

55: If w0 is not equal to 0, go to .L4

56: Loads the first part of the address of the "You win" string(.LC0) into x0

57: Loads the second part of the address of the "You win" string(.LC0) into x0

58: calls the puts function with x0 as argument to print "You win"

59: goes to .L6 to avoid running .L4
```

We can see that .LC0 and .LC1 contain the "You win" and "You lose :(" strings respectively.

.L4 just prints the "You lose :(" string when it is called

.L6 will clean up the stack and will return from the main function.

As we can see, the main function just serves the function of calling func with the 1st argument we pass into the function and prints "You win" if it returns 0.

We can now analyse func in a similar manner to realise that all func does is it calculates and returns 27-w0. Thus, we can see that to get the win condition, we must simply input 27 into the program. Thus, we can get our flag.

## Flag:

```
picoCTF{0000001b}
```

## Concepts learnt:

- Learned so much about arm assembly that it would be impossible to put here.

## Resources:

- [reverse engineering makes you a better programmer](https://www.youtube.com/watch?v=1d-6Hv1c39c)

***

# 3. Vauld door 3

This vault uses for-loops and byte arrays. The source code for this vault is here: [VaultDoor3.java](RE/VaultDoor3.java)

## Solution:

In this challenge, we have been given a java file. To solve this challenge, we need to understand what the code does and figure out what the required password is. Then, we must convert the required password into the flag format by putting it between `picoCTF{` and `}`. This will give us the correct flag.

<details closed>
<summary><i>VaultDoor3.java</i></summary>

```java
 1  import java.util.*;
 2
 3  class VaultDoor3 {
 4      public static void main(String args[]) {
 5          VaultDoor3 vaultDoor = new VaultDoor3();
 6          Scanner scanner = new Scanner(System.in);
 7          System.out.print("Enter vault password: ");
 8          String userInput = scanner.next();
 9          String input = userInput.substring("picoCTF{".length(),userInput.length()-1);
10          if (vaultDoor.checkPassword(input)) {
11              System.out.println("Access granted.");
12          } else {
13              System.out.println("Access denied!");
14          }
15      }
16
17      // Our security monitoring team has noticed some intrusions on some of the
18      // less secure doors. Dr. Evil has asked me specifically to build a stronger
19      // vault door to protect his Doomsday plans. I just *know* this door will
20      // keep all of those nosy agents out of our business. Mwa ha!
21      //
22      // -Minion #2671
23      public boolean checkPassword(String password) {
24          if (password.length() != 32) {
25              return false;
26          }
27          char[] buffer = new char[32];
28          int i;
29          for (i=0; i<8; i++) {
30              buffer[i] = password.charAt(i);
31          }
32          for (; i<16; i++) {
33              buffer[i] = password.charAt(23-i);
34          }
35          for (; i<32; i+=2) {
36              buffer[i] = password.charAt(46-i);
37          }
38          for (i=31; i>=17; i-=2) {
39              buffer[i] = password.charAt(i);
40          }
41          String s = new String(buffer);
42          return s.equals("jU5t_a_sna_3lpm18g947_u_4_m9r54f");
43      }
44  }
```

</details>

On looking at the `checkPassword` function, it is easy to deduce how the input string is being manipulated and then compared to a scrambled version of the password `jU5t_a_sna_3lpm18g947_u_4_m9r54f`. We can very easily unscramble the password, either by doing it manually, or by using some simple code. On doing it manually, the unscrambled password came out to be `jU5t_a_s1mpl3_an4gr4m_4_u_79958f` which allows us to get the flag `picoCTF{jU5t_a_s1mpl3_an4gr4m_4_u_79958f}`.

## Flag:

```
picoCTF{jU5t_a_s1mpl3_an4gr4m_4_u_79958f}
```

## Concepts learnt:

- Absolutely nothing tbh
