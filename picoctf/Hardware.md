# 1. IQ Test

## Description:

let your input x = 30478191278.

wrap your answer with nite{ } for the flag.

As an example, entering x = 34359738368 gives (y0, ..., y11), so the flag would be nite{010000000011}.

![iqtest.png](H/iqtest.png)

## Solution:

![iqtest-soln.png](H/iqtest-soln.png)

## Flag:

```
nite{100010011000}
```

## Concepts learnt:

- E

***

# 2. I like Logic

## Description:

i like logic and i like files, apparently, they have something in common, what should my next step be.

## Solution:
In this challenge, we have been given a `.sal` file. If we search about it on google, we should be able to find that the file is actually used with a software called `Logic 2` by a company called `saleae`. If we open the file in that software, we will be greeted with an oscilloscope like interface with a signal being present on channel 3.

To analyse the signal, we must first find the baud rate of the signal. The baud rate is equal to the inverse of the smallest pulse bit present in the signal which in this case, was equal to `104μs`. This gives us a calculated baud rate of `9615.3846`. This is very close to the commonly used `9600` baud rate so we can assume a margin of error and use that instead.

Now, we can add an `Async Serial analyser` to the signal with the correct baud rate. If we now look at the analysers pane on the right, and switch to the terminal view, we should be able to see the signal output.

<details closed>
<summary><i>Signal Message</i></summary>

```
on't think he makes any claims of
that kind.  But I do believe he has got something new."

"Then for Heaven's sake, man, write it up!"

"I'm longing to, but all I know he gave me in confidence and on
condition that I didn't."  I condensed into a few sentences the
Professor's narrative.  "That's how it stands."

McArdle looked deeply incredulous.

"Well, Mr. Malone," he said at last, "about this scientific meeting
to-night; there can be no privacy about that, anyhow.  I don't suppose
any paper will want to report it, for Waldron has been reported already
a dozen times, and no one is aware that Challenger will speak.  We may
get a scoop, if we are lucky.  You'll be there in any case, so you'll
just give us a pretty full report.  I'll keep space up to midnight."

My day was a busy one, and I had an early dinner at the Savage Club
with Tarp Henry, to whom I gave some account of my adventures.  He
listened with a sceptical smile on his gaunt face, and roared with
laughter on hearing that the Professor had convinced me.

"My dear chap, things don't happen like that in real life.  People
don't stumble upon enormous discoveries and then lose their evidence.
Leave that to the novelists.  The fellow is as full of tricks as the
monkey-house at the Zoo.  It's all bosh."

"But the American poet?"

"He never existed."

"I saw his sketch-book."

"Challenger's sketch-book."

"You think he drew that animal?"

"Of course he did.  Who else?"

"Well, then, the photographs?"

"There was nothing in the photographs.  By your own admission you only
saw a bird."

FCSC{b1dee4eeadf6c4e60aeb142b0b486344e64b12b40d1046de95c89ba5e23a9925}

"A pterodactyl."

"That's what HE says.  He put the pterodactyl into your head."

"Well, then, the bones?"

"First one out of an Irish stew.  Second one vamped up for the
occasion.  If you are clever and know your business you can fake a bone
as easily as you can a photograph."

I began to feel uneasy.  Perhaps, after all, I had been premature in my
acquiescence.  Then I had a sudden happy thought.

"Will you come to the meeting?" I asked.

Tarp Henry looked thoughtful.

"He is not a popular person, the genial Challenger," said he.  "A lot
of people have accounts to settle with him.  I should say he is about
the best-hated man in London.  If the medical students turn out there
will be no end of a rag.  I don't want to get into a bear-garden."

"You might at least do him the justice to hear him state his own case."

"Well, perhaps it's only fair.  All right.  I'm your man for the
evening."

When we arrived at the hall we found a much greater concourse than I
had expected.  A line of electric broughams discharged their little
cargoes of white-bearded professors, while the dark stream of humbler
pedestrians, who crowded through the arched door-way, showed that the
audience would be popular as well as scientific.  Indeed, it became
evident to us as soon as we had taken our seats that a youthful and
even boyish spirit was abroad in the gallery and the back portions of
the hall.  Looking behind me, I could see rows of faces of the familiar
medical student type.  Apparently the great hospitals had each sent
down their contingent.  The behavior of the audience at present was
good-humored, but mischievous.  Scraps of popular songs were chorused
with an enthusiasm which was a strange prelude to a scientific lecture,
and there was already a tendency to personal chaff which promised a
jovial evening to others, however embarrassing it might be to the
recipients of these dubious honors.

Thus, when old Doctor Meldrum, with his well-known curly-brimmed
opera-hat, appeared upon the platform, there was such a universal query
of "Where DID you get that tile?" that he hurriedly removed it, and
concealed it furtively under his chair.  When gouty Professor Wadley
limped down to his seat there were general affectionate inquiries from
all parts of the hall as to the exact state of his poor toe, which
caused him obvious embarrassment.  The greatest demonstration of all,
however, was at the entrance of my new acquaintance, Professor
Challenger, when he passed down to take his place at the extreme end of
the front row of the platform.  Such a yell of welcome broke forth when
his black beard first protruded round the corner that I began to
suspect Tarp Henry was right in his surmise, and that this assemblage
was there not merely for the sake of the lecture, but because it had
got rumored abroad that the famous Professor would take part in the
proceedings.

There was some sympathetic laughter on his entrance among the front
benches of well-dressed spectators, as though the demonstration of the
students in this instance was not unwelcome to them.  That greeting
was, indeed, a frightful outburst of sound, the uproar of the carnivora
cage when the step of the bucket-bearing keeper is heard in the
distance.  There was an offensive tone in it, perhaps, and yet in the
main it struck me as mere riotous outcry, the noisy reception of one
who amused and interested them, rather than of one they disliked or
despised.  Challenger smiled with weary and tolerant contempt, as a
kindly man would meet the yapping of a litter of puppies.  He sat
slowly down, blew out his chest, passed his hand caressingly down his
beard, and looked with drooping eyelids and supercilious eyes at the
crowded hall before him.  The uproar of his advent had not yet died
away when Professor Ronald Murray, the chairman, and Mr. Waldron, the
lecturer, threaded their way to the front, and the proceedings began.

Professor Murray will, I am sure, excuse me if I say that he has the
common fault of most Englishmen of being inaudible.  Why on earth
people who have something to say which is worth hearing should not take
the slight trouble to learn how to make it heard is one of the strange
mysteries of modern life.  Their methods are as reasonable as to try to
pour some precious stuff from the spring to the reservoir through a
non-conducting pipe, which could by the least effort be opened.
Professor Murray made several profound remarks to his white tie and to
the water-carafe upon the table, with a humorous, twinkling aside to
the silver candlestick upon his right.  Then he sat down, and Mr.
Waldron, the famous popular lecturer, rose amid a general murmur of
applause.  He was a stern, gaunt man, with a harsh voice, and an
aggressive manner, but he had the merit of knowing how to assimilate
the ideas of other men, and to pass them on in a way which was
intelligible and even interesting to the lay public, with a happy knack
of being funny about the most unlikely objects, so that the precession
of the Equinox or the formation of a vertebrate became a highly
humorous process as treated by him.

It was a bird's-eye view of creation, as interpreted by science, which,
in language always clear and sometimes picturesque, he unfolded before
us.  He told us of t
```

</details>

Here, we can see that the flag is `FCSC{b1dee4eeadf6c4e60aeb142b0b486344e64b12b40d1046de95c89ba5e23a9925}`.

## Flag:

```
FCSC{b1dee4eeadf6c4e60aeb142b0b486344e64b12b40d1046de95c89ba5e23a9925}
```

## Concepts learnt:

- how to analyse signals ig

***

# 3. Bare Metal Alchemist

## Description:

my friend recommended me this anime but i think i've heard a wrong name.

## Solution:

In this challenge, we have been given a mysterious `firmware.elf` file. If we use the `file` command on it, we can see that it is actually a `Atmel AVR 8-bit executable`.

```sh
$ file firmware.elf 
firmware.elf: ELF 32-bit LSB executable, Atmel AVR 8-bit, version 1 (SYSV), statically linked, with debug_info, not stripped
```

We can try to see if using `strings` on it gives us anything useful.

<details closed>
<summary><i>strings firmware.elf</i></summary>

```sh
$ strings firmware.elf 
[Ofm}
w|9^yq=t
w|9^yq=t
GCC: (GNU) 7.3.0
atmega328p
../../../../gcc/libgcc/config/avr/lib1funcs.S
/home/jenkins/workspace/avr-gcc-staging/label/debian7-x86_64/gcc-build/avr/avr5/libgcc
GNU AS 2.26
../../../../gcc/libgcc/config/avr/lib1funcs.S
/home/jenkins/workspace/avr-gcc-staging/label/debian7-x86_64/gcc-build/avr/avr5/libgcc
GNU AS 2.26
../../../../gcc/libgcc/config/avr/lib1funcs.S
/home/jenkins/workspace/avr-gcc-staging/label/debian7-x86_64/gcc-build/avr/avr5/libgcc
GNU AS 2.26
../../../../gcc/libgcc/config/avr
lib1funcs.S
../../../../gcc/libgcc/config/avr
lib1funcs.S
../../../../gcc/libgcc/config/avr
lib1funcs.S
avr-libc 2.0.0
uint8_t
uint16_t
__eeprom
UDR0
UCSR0A
UCSR0B
UCSR0C
UBRR0
TWAMR
TWBR
TWCR
TWSR
TWDR
TWAR
TIMSK1
TIFR1
TCCR1A
TCCR1B
TCCR1C
TCNT1
OCR1A
OCR1B
ICR1
GTCCR
TIMSK2
TIFR2
TCCR2A
TCCR2B
TCNT2
OCR2B
OCR2A
ASSR
GTCCR
ADMUX
ADCSRA
ADCSRB
DIDR0
ACSR
DIDR1
PORTB
DDRB
PINB
PORTC
DDRC
PINC
PORTD
DDRD
PIND
OCR0B
OCR0A
TCNT0
TCCR0B
TCCR0A
TIMSK0
TIFR0
GTCCR
EICRA
EIMSK
EIFR
PCICR
PCMSK2
PCMSK1
PCMSK0
PCIFR
SPDR
SPSR
SPCR
WDTCSR
OSCCAL
CLKPR
SREG
SPMCSR
MCUCR
MCUSR
SMCR
GPIOR2
GPIOR1
GPIOR0
EEAR
EEDR
EECR
__SP_H__
__SP_L__
__SREG__
__tmp_reg__
__zero_reg__
_ZL2z1v
timer0_millis
timer0_fract
timer0_overflow_count
_ZL2Xf
CSWTCH.14
_clear_bss.o
.do_clear_bss_start
.do_clear_bss_loop
_exit.o
__stop_program
__vector_22
__vector_1
__DATA_REGION_LENGTH__
__trampolines_start
_etext
__vector_24
__vector_12
__bad_interrupt
__data_load_end
__vector_6
__trampolines_end
__vector_3
__vector_23
__data_load_start
__dtors_end
__bss_end
__LOCK_REGION_LENGTH__
__vector_25
__vector_11
__init
_Z14serialEventRunv
__vector_13
__vector_17
__vector_19
__vector_7
__do_clear_bss
__eeprom_end
__vectors
__data_end
__vector_default
__vector_5
__SIGNATURE_REGION_LENGTH__
__ctors_start
__do_copy_data
__bss_start
main
__vector_4
__heap_end
__vector_9
__vector_2
__USER_SIGNATURE_REGION_LENGTH__
__vector_21
__vector_15
__dtors_start
__ctors_end
__stack
_edata
__vector_8
__EEPROM_REGION_LENGTH__
_exit
__vector_14
__vector_10
__vector_16
__data_start
__vector_18
__FUSE_REGION_LENGTH__
__TEXT_REGION_LENGTH__
__vector_20
.symtab
.strtab
.shstrtab
.data
.text
.bss
.comment
.note.gnu.avr.deviceinfo
.debug_aranges
.debug_info
.debug_abbrev
.debug_line
.debug_str
```

</details>

Here, we can see that it is actually the firmware of an `atmega 328p` that has been compiled using `gcc`. It is the same processor used on the `arduino uno`. I tried to use an arduino uno simulator to see if I could get the flag that way but I couldnt get it to work.

We can try to use `avr-objdump` to disassemble the binary.


<details closed>
<summary><i>assembly</i></summary>

```as
$ avr-objdump -d firmware.elf

firmware.elf:     file format elf32-avr


Disassembly of section .text:

00000000 <__vectors>:
   0:   0c 94 4b 00     jmp     0x96    ; 0x96 <__ctors_end>
   4:   0c 94 68 00     jmp     0xd0    ; 0xd0 <__bad_interrupt>
   8:   0c 94 68 00     jmp     0xd0    ; 0xd0 <__bad_interrupt>
   c:   0c 94 68 00     jmp     0xd0    ; 0xd0 <__bad_interrupt>
  10:   0c 94 68 00     jmp     0xd0    ; 0xd0 <__bad_interrupt>
  14:   0c 94 68 00     jmp     0xd0    ; 0xd0 <__bad_interrupt>
  18:   0c 94 68 00     jmp     0xd0    ; 0xd0 <__bad_interrupt>
  1c:   0c 94 68 00     jmp     0xd0    ; 0xd0 <__bad_interrupt>
  20:   0c 94 68 00     jmp     0xd0    ; 0xd0 <__bad_interrupt>
  24:   0c 94 68 00     jmp     0xd0    ; 0xd0 <__bad_interrupt>
  28:   0c 94 68 00     jmp     0xd0    ; 0xd0 <__bad_interrupt>
  2c:   0c 94 68 00     jmp     0xd0    ; 0xd0 <__bad_interrupt>
  30:   0c 94 68 00     jmp     0xd0    ; 0xd0 <__bad_interrupt>
  34:   0c 94 68 00     jmp     0xd0    ; 0xd0 <__bad_interrupt>
  38:   0c 94 68 00     jmp     0xd0    ; 0xd0 <__bad_interrupt>
  3c:   0c 94 68 00     jmp     0xd0    ; 0xd0 <__bad_interrupt>
  40:   0c 94 71 00     jmp     0xe2    ; 0xe2 <__vector_16>
  44:   0c 94 68 00     jmp     0xd0    ; 0xd0 <__bad_interrupt>
  48:   0c 94 68 00     jmp     0xd0    ; 0xd0 <__bad_interrupt>
  4c:   0c 94 68 00     jmp     0xd0    ; 0xd0 <__bad_interrupt>
  50:   0c 94 68 00     jmp     0xd0    ; 0xd0 <__bad_interrupt>
  54:   0c 94 68 00     jmp     0xd0    ; 0xd0 <__bad_interrupt>
  58:   0c 94 68 00     jmp     0xd0    ; 0xd0 <__bad_interrupt>
  5c:   0c 94 68 00     jmp     0xd0    ; 0xd0 <__bad_interrupt>
  60:   0c 94 68 00     jmp     0xd0    ; 0xd0 <__bad_interrupt>
  64:   0c 94 68 00     jmp     0xd0    ; 0xd0 <__bad_interrupt>

00000068 <_ZL2Xf>:
  68:   f1 e3 e6 e6 f1 e3 de f1 cd 94 d6 fa 94 d6 fa d6     ................
  78:   ca c8 96 fa d6 94 c8 d5 c9 96 fa 91 d7 c1 d0 94     ................
  88:   cb ca fa c3 94 d7 c8 d2 91 d7 c0 d8 00 00           ..............

00000096 <__ctors_end>:
  96:   11 24           eor     r1, r1
  98:   1f be           out     0x3f, r1        ; 63
  9a:   cf ef           ldi     r28, 0xFF       ; 255
  9c:   d8 e0           ldi     r29, 0x08       ; 8
  9e:   de bf           out     0x3e, r29       ; 62
  a0:   cd bf           out     0x3d, r28       ; 61

000000a2 <__do_copy_data>:
  a2:   11 e0           ldi     r17, 0x01       ; 1
  a4:   a0 e0           ldi     r26, 0x00       ; 0
  a6:   b1 e0           ldi     r27, 0x01       ; 1
  a8:   e4 ee           ldi     r30, 0xE4       ; 228
  aa:   f2 e0           ldi     r31, 0x02       ; 2
  ac:   02 c0           rjmp    .+4             ; 0xb2 <__do_copy_data+0x10>
  ae:   05 90           lpm     r0, Z+
  b0:   0d 92           st      X+, r0
  b2:   ae 34           cpi     r26, 0x4E       ; 78
  b4:   b1 07           cpc     r27, r17
  b6:   d9 f7           brne    .-10            ; 0xae <__do_copy_data+0xc>

000000b8 <__do_clear_bss>:
  b8:   21 e0           ldi     r18, 0x01       ; 1
  ba:   ae e4           ldi     r26, 0x4E       ; 78
  bc:   b1 e0           ldi     r27, 0x01       ; 1
  be:   01 c0           rjmp    .+2             ; 0xc2 <.do_clear_bss_start>

000000c0 <.do_clear_bss_loop>:
  c0:   1d 92           st      X+, r1

000000c2 <.do_clear_bss_start>:
  c2:   a7 35           cpi     r26, 0x57       ; 87
  c4:   b2 07           cpc     r27, r18
  c6:   e1 f7           brne    .-8             ; 0xc0 <.do_clear_bss_loop>
  c8:   0e 94 bb 00     call    0x176   ; 0x176 <main>
  cc:   0c 94 70 01     jmp     0x2e0   ; 0x2e0 <_exit>

000000d0 <__bad_interrupt>:
  d0:   0c 94 00 00     jmp     0       ; 0x0 <__vectors>

000000d4 <_ZL2z1v>:
  d4:   8b b1           in      r24, 0x0b       ; 11
  d6:   87 70           andi    r24, 0x07       ; 7
  d8:   8b b9           out     0x0b, r24       ; 11
  da:   85 b1           in      r24, 0x05       ; 5
  dc:   8c 7f           andi    r24, 0xFC       ; 252
  de:   85 b9           out     0x05, r24       ; 5
  e0:   08 95           ret

000000e2 <__vector_16>:
  e2:   1f 92           push    r1
  e4:   0f 92           push    r0
  e6:   0f b6           in      r0, 0x3f        ; 63
  e8:   0f 92           push    r0
  ea:   11 24           eor     r1, r1
  ec:   2f 93           push    r18
  ee:   3f 93           push    r19
  f0:   8f 93           push    r24
  f2:   9f 93           push    r25
  f4:   af 93           push    r26
  f6:   bf 93           push    r27
  f8:   80 91 53 01     lds     r24, 0x0153     ; 0x800153 <timer0_millis>
  fc:   90 91 54 01     lds     r25, 0x0154     ; 0x800154 <timer0_millis+0x1>
 100:   a0 91 55 01     lds     r26, 0x0155     ; 0x800155 <timer0_millis+0x2>
 104:   b0 91 56 01     lds     r27, 0x0156     ; 0x800156 <timer0_millis+0x3>
 108:   30 91 52 01     lds     r19, 0x0152     ; 0x800152 <timer0_fract>
 10c:   23 e0           ldi     r18, 0x03       ; 3
 10e:   23 0f           add     r18, r19
 110:   2d 37           cpi     r18, 0x7D       ; 125
 112:   58 f5           brcc    .+86            ; 0x16a <__vector_16+0x88>
 114:   01 96           adiw    r24, 0x01       ; 1
 116:   a1 1d           adc     r26, r1
 118:   b1 1d           adc     r27, r1
 11a:   20 93 52 01     sts     0x0152, r18     ; 0x800152 <timer0_fract>
 11e:   80 93 53 01     sts     0x0153, r24     ; 0x800153 <timer0_millis>
 122:   90 93 54 01     sts     0x0154, r25     ; 0x800154 <timer0_millis+0x1>
 126:   a0 93 55 01     sts     0x0155, r26     ; 0x800155 <timer0_millis+0x2>
 12a:   b0 93 56 01     sts     0x0156, r27     ; 0x800156 <timer0_millis+0x3>
 12e:   80 91 4e 01     lds     r24, 0x014E     ; 0x80014e <timer0_overflow_count>
 132:   90 91 4f 01     lds     r25, 0x014F     ; 0x80014f <timer0_overflow_count+0x1>
 136:   a0 91 50 01     lds     r26, 0x0150     ; 0x800150 <timer0_overflow_count+0x2>
 13a:   b0 91 51 01     lds     r27, 0x0151     ; 0x800151 <timer0_overflow_count+0x3>
 13e:   01 96           adiw    r24, 0x01       ; 1
 140:   a1 1d           adc     r26, r1
 142:   b1 1d           adc     r27, r1
 144:   80 93 4e 01     sts     0x014E, r24     ; 0x80014e <timer0_overflow_count>
 148:   90 93 4f 01     sts     0x014F, r25     ; 0x80014f <timer0_overflow_count+0x1>
 14c:   a0 93 50 01     sts     0x0150, r26     ; 0x800150 <timer0_overflow_count+0x2>
 150:   b0 93 51 01     sts     0x0151, r27     ; 0x800151 <timer0_overflow_count+0x3>
 154:   bf 91           pop     r27
 156:   af 91           pop     r26
 158:   9f 91           pop     r25
 15a:   8f 91           pop     r24
 15c:   3f 91           pop     r19
 15e:   2f 91           pop     r18
 160:   0f 90           pop     r0
 162:   0f be           out     0x3f, r0        ; 63
 164:   0f 90           pop     r0
 166:   1f 90           pop     r1
 168:   18 95           reti
 16a:   26 e8           ldi     r18, 0x86       ; 134
 16c:   23 0f           add     r18, r19
 16e:   02 96           adiw    r24, 0x02       ; 2
 170:   a1 1d           adc     r26, r1
 172:   b1 1d           adc     r27, r1
 174:   d2 cf           rjmp    .-92            ; 0x11a <__vector_16+0x38>

00000176 <main>:
 176:   cf 93           push    r28
 178:   df 93           push    r29
 17a:   00 d0           rcall   .+0             ; 0x17c <main+0x6>
 17c:   cd b7           in      r28, 0x3d       ; 61
 17e:   de b7           in      r29, 0x3e       ; 62
 180:   78 94           sei
 182:   84 b5           in      r24, 0x24       ; 36
 184:   82 60           ori     r24, 0x02       ; 2
 186:   84 bd           out     0x24, r24       ; 36
 188:   84 b5           in      r24, 0x24       ; 36
 18a:   81 60           ori     r24, 0x01       ; 1
 18c:   84 bd           out     0x24, r24       ; 36
 18e:   85 b5           in      r24, 0x25       ; 37
 190:   82 60           ori     r24, 0x02       ; 2
 192:   85 bd           out     0x25, r24       ; 37
 194:   85 b5           in      r24, 0x25       ; 37
 196:   81 60           ori     r24, 0x01       ; 1
 198:   85 bd           out     0x25, r24       ; 37
 19a:   80 91 6e 00     lds     r24, 0x006E     ; 0x80006e <__TEXT_REGION_LENGTH__+0x7e006e>
 19e:   81 60           ori     r24, 0x01       ; 1
 1a0:   80 93 6e 00     sts     0x006E, r24     ; 0x80006e <__TEXT_REGION_LENGTH__+0x7e006e>
 1a4:   10 92 81 00     sts     0x0081, r1      ; 0x800081 <__TEXT_REGION_LENGTH__+0x7e0081>
 1a8:   80 91 81 00     lds     r24, 0x0081     ; 0x800081 <__TEXT_REGION_LENGTH__+0x7e0081>
 1ac:   82 60           ori     r24, 0x02       ; 2
 1ae:   80 93 81 00     sts     0x0081, r24     ; 0x800081 <__TEXT_REGION_LENGTH__+0x7e0081>
 1b2:   80 91 81 00     lds     r24, 0x0081     ; 0x800081 <__TEXT_REGION_LENGTH__+0x7e0081>
 1b6:   81 60           ori     r24, 0x01       ; 1
 1b8:   80 93 81 00     sts     0x0081, r24     ; 0x800081 <__TEXT_REGION_LENGTH__+0x7e0081>
 1bc:   80 91 80 00     lds     r24, 0x0080     ; 0x800080 <__TEXT_REGION_LENGTH__+0x7e0080>
 1c0:   81 60           ori     r24, 0x01       ; 1
 1c2:   80 93 80 00     sts     0x0080, r24     ; 0x800080 <__TEXT_REGION_LENGTH__+0x7e0080>
 1c6:   80 91 b1 00     lds     r24, 0x00B1     ; 0x8000b1 <__TEXT_REGION_LENGTH__+0x7e00b1>
 1ca:   84 60           ori     r24, 0x04       ; 4
 1cc:   80 93 b1 00     sts     0x00B1, r24     ; 0x8000b1 <__TEXT_REGION_LENGTH__+0x7e00b1>
 1d0:   80 91 b0 00     lds     r24, 0x00B0     ; 0x8000b0 <__TEXT_REGION_LENGTH__+0x7e00b0>
 1d4:   81 60           ori     r24, 0x01       ; 1
 1d6:   80 93 b0 00     sts     0x00B0, r24     ; 0x8000b0 <__TEXT_REGION_LENGTH__+0x7e00b0>
 1da:   80 91 7a 00     lds     r24, 0x007A     ; 0x80007a <__TEXT_REGION_LENGTH__+0x7e007a>
 1de:   84 60           ori     r24, 0x04       ; 4
 1e0:   80 93 7a 00     sts     0x007A, r24     ; 0x80007a <__TEXT_REGION_LENGTH__+0x7e007a>
 1e4:   80 91 7a 00     lds     r24, 0x007A     ; 0x80007a <__TEXT_REGION_LENGTH__+0x7e007a>
 1e8:   82 60           ori     r24, 0x02       ; 2
 1ea:   80 93 7a 00     sts     0x007A, r24     ; 0x80007a <__TEXT_REGION_LENGTH__+0x7e007a>
 1ee:   80 91 7a 00     lds     r24, 0x007A     ; 0x80007a <__TEXT_REGION_LENGTH__+0x7e007a>
 1f2:   81 60           ori     r24, 0x01       ; 1
 1f4:   80 93 7a 00     sts     0x007A, r24     ; 0x80007a <__TEXT_REGION_LENGTH__+0x7e007a>
 1f8:   80 91 7a 00     lds     r24, 0x007A     ; 0x80007a <__TEXT_REGION_LENGTH__+0x7e007a>
 1fc:   80 68           ori     r24, 0x80       ; 128
 1fe:   80 93 7a 00     sts     0x007A, r24     ; 0x80007a <__TEXT_REGION_LENGTH__+0x7e007a>
 202:   10 92 c1 00     sts     0x00C1, r1      ; 0x8000c1 <__TEXT_REGION_LENGTH__+0x7e00c1>
 206:   8a b1           in      r24, 0x0a       ; 10
 208:   88 6f           ori     r24, 0xF8       ; 248
 20a:   8a b9           out     0x0a, r24       ; 10
 20c:   84 b1           in      r24, 0x04       ; 4
 20e:   83 60           ori     r24, 0x03       ; 3
 210:   84 b9           out     0x04, r24       ; 4
 212:   52 98           cbi     0x0a, 2 ; 10
 214:   8b b1           in      r24, 0x0b       ; 11
 216:   87 70           andi    r24, 0x07       ; 7
 218:   8b b9           out     0x0b, r24       ; 11
 21a:   85 b1           in      r24, 0x05       ; 5
 21c:   8c 7f           andi    r24, 0xFC       ; 252
 21e:   85 b9           out     0x05, r24       ; 5
 220:   95 ea           ldi     r25, 0xA5       ; 165
 222:   b9 2e           mov     r11, r25
 224:   20 e0           ldi     r18, 0x00       ; 0
 226:   c2 2e           mov     r12, r18
 228:   20 e0           ldi     r18, 0x00       ; 0
 22a:   d2 2e           mov     r13, r18
 22c:   89 b1           in      r24, 0x09       ; 9
 22e:   98 2f           mov     r25, r24
 230:   99 0f           add     r25, r25
 232:   89 27           eor     r24, r25
 234:   82 ff           sbrs    r24, 2
 236:   23 c0           rjmp    .+70            ; 0x27e <main+0x108>
 238:   88 e6           ldi     r24, 0x68       ; 104
 23a:   e8 2e           mov     r14, r24
 23c:   80 e0           ldi     r24, 0x00       ; 0
 23e:   f8 2e           mov     r15, r24
 240:   00 e0           ldi     r16, 0x00       ; 0
 242:   f7 01           movw    r30, r14
 244:   84 91           lpm     r24, Z
 246:   88 23           and     r24, r24
 248:   61 f0           breq    .+24            ; 0x262 <main+0xec>
 24a:   e8 2f           mov     r30, r24
 24c:   eb 25           eor     r30, r11
 24e:   85 3a           cpi     r24, 0xA5       ; 165
 250:   41 f0           breq    .+16            ; 0x262 <main+0xec>
 252:   89 b1           in      r24, 0x09       ; 9
 254:   98 2f           mov     r25, r24
 256:   99 0f           add     r25, r25
 258:   89 27           eor     r24, r25
 25a:   82 fd           sbrc    r24, 2
 25c:   18 c0           rjmp    .+48            ; 0x28e <main+0x118>
 25e:   0e 94 6a 00     call    0xd4    ; 0xd4 <_ZL2z1v>
 262:   1a 82           std     Y+2, r1 ; 0x02
 264:   19 82           std     Y+1, r1 ; 0x01
 266:   89 81           ldd     r24, Y+1        ; 0x01
 268:   9a 81           ldd     r25, Y+2        ; 0x02
 26a:   8c 32           cpi     r24, 0x2C       ; 44
 26c:   91 40           sbci    r25, 0x01       ; 1
 26e:   48 f4           brcc    .+18            ; 0x282 <main+0x10c>
 270:   00 00           nop
 272:   89 81           ldd     r24, Y+1        ; 0x01
 274:   9a 81           ldd     r25, Y+2        ; 0x02
 276:   01 96           adiw    r24, 0x01       ; 1
 278:   9a 83           std     Y+2, r25        ; 0x02
 27a:   89 83           std     Y+1, r24        ; 0x01
 27c:   f4 cf           rjmp    .-24            ; 0x266 <main+0xf0>
 27e:   0e 94 6a 00     call    0xd4    ; 0xd4 <_ZL2z1v>
 282:   c1 14           cp      r12, r1
 284:   d1 04           cpc     r13, r1
 286:   91 f2           breq    .-92            ; 0x22c <main+0xb6>
 288:   0e 94 00 00     call    0       ; 0x0 <__vectors>
 28c:   cf cf           rjmp    .-98            ; 0x22c <main+0xb6>
 28e:   e0 53           subi    r30, 0x30       ; 48
 290:   10 e0           ldi     r17, 0x00       ; 0
 292:   ee 34           cpi     r30, 0x4E       ; 78
 294:   20 f4           brcc    .+8             ; 0x29e <main+0x128>
 296:   f0 e0           ldi     r31, 0x00       ; 0
 298:   e0 50           subi    r30, 0x00       ; 0
 29a:   ff 4f           sbci    r31, 0xFF       ; 255
 29c:   10 81           ld      r17, Z
 29e:   0e 94 6a 00     call    0xd4    ; 0xd4 <_ZL2z1v>
 2a2:   10 fd           sbrc    r17, 0
 2a4:   5b 9a           sbi     0x0b, 3 ; 11
 2a6:   11 fd           sbrc    r17, 1
 2a8:   5c 9a           sbi     0x0b, 4 ; 11
 2aa:   12 fd           sbrc    r17, 2
 2ac:   5d 9a           sbi     0x0b, 5 ; 11
 2ae:   13 fd           sbrc    r17, 3
 2b0:   5e 9a           sbi     0x0b, 6 ; 11
 2b2:   14 fd           sbrc    r17, 4
 2b4:   5f 9a           sbi     0x0b, 7 ; 11
 2b6:   15 fd           sbrc    r17, 5
 2b8:   28 9a           sbi     0x05, 0 ; 5
 2ba:   16 fd           sbrc    r17, 6
 2bc:   29 9a           sbi     0x05, 1 ; 5
 2be:   80 2f           mov     r24, r16
 2c0:   8f 71           andi    r24, 0x1F       ; 31
 2c2:   83 5d           subi    r24, 0xD3       ; 211
 2c4:   81 50           subi    r24, 0x01       ; 1
 2c6:   38 f0           brcs    .+14            ; 0x2d6 <main+0x160>
 2c8:   ef e9           ldi     r30, 0x9F       ; 159
 2ca:   ff e0           ldi     r31, 0x0F       ; 15
 2cc:   31 97           sbiw    r30, 0x01       ; 1
 2ce:   f1 f7           brne    .-4             ; 0x2cc <main+0x156>
 2d0:   00 c0           rjmp    .+0             ; 0x2d2 <main+0x15c>
 2d2:   00 00           nop
 2d4:   f7 cf           rjmp    .-18            ; 0x2c4 <main+0x14e>
 2d6:   ff ef           ldi     r31, 0xFF       ; 255
 2d8:   ef 1a           sub     r14, r31
 2da:   ff 0a           sbc     r15, r31
 2dc:   0b 5d           subi    r16, 0xDB       ; 219
 2de:   b1 cf           rjmp    .-158           ; 0x242 <main+0xcc>

000002e0 <_exit>:
 2e0:   f8 94           cli

000002e2 <__stop_program>:
 2e2:   ff cf           rjmp    .-2             ; 0x2e2 <__stop_program>
```

</details>

Something that drew my attention was this large block of data.

```
00000068 <_ZL2Xf>:
  68:   f1 e3 e6 e6 f1 e3 de f1 cd 94 d6 fa 94 d6 fa d6     ................
  78:   ca c8 96 fa d6 94 c8 d5 c9 96 fa 91 d7 c1 d0 94     ................
  88:   cb ca fa c3 94 d7 c8 d2 91 d7 c0 d8 00 00           ..............
```

If we put this into cyberchef in the form

```
f1 e3 e6 e6 f1 e3 de f1 cd 94 d6 fa 94 d6 fa d6 ca c8 96 fa d6 94 c8 d5 c9 96 fa 91 d7 c1 d0 94 cb ca fa c3 94 d7 c8 d2 91 d7 c0 d8 00
```

and then do a `From Hex` followed by a `Magic` in intensive mode and with just `{` as the Crib, it will give us the flag.

## Flag:

```
TFCCTF{Th1s_1s_som3_s1mpl3_4rdu1no_f1rmw4re}
```

## Concepts learnt:

- idk
