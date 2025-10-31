# 1. Trivial Flag Transfer Protocol

## Description:

Figure out how they moved the [flag](F/tftp.pcapng).

## Solution:

For this challenge, we can't use the latest version of `wireshark`. but rather, we must use an older version such as `4.4.5`. We have been provided with a `.pcapng` file which we must open in wireshark to analyse. Then, we can export all the tftp objects by going to `File>Export Objects>TFTP...` in the global menu and selecting any suitable location.

This will give us the following files:

[instructions.txt](F/TFTP/instructions.txt)
[plan](F/TFTP/plan)
[program.deb](F/TFTP/program.deb)
![picture1.bmp](F/TFTP/picture1.bmp)
![picture2.bmp](F/TFTP/picture2.bmp)
![picture3.bmp](F/TFTP/picture3.bmp)

If we open `instructions.txt`, then we will see the following text: `GSGCQBRFAGRAPELCGBHEGENSSVPFBJRZHFGQVFTHVFRBHESYNTGENAFSRE.SVTHERBHGNJNLGBUVQRGURSYNTNAQVJVYYPURPXONPXSBEGURCYNA`.

If we paste this text into `CyberChef` and use the `Rot13` operation, we will get the text `TFTPDOESNTENCRYPTOURTRAFFICSOWEMUSTDISGUISEOURFLAGTRANSFER.FIGUREOUTAWAYTOHIDETHEFLAGANDIWILLCHECKBACKFORTHEPLAN`.

On making it more readable, it will look like this: `TFTP doesn't encrypt our traffic so we must disguise our flag transfer. Figure out a way to hide the flag and i will check back for the plan`

Now, if we open the `plan` file, we will see: `VHFRQGURCEBTENZNAQUVQVGJVGU-QHRQVYVTRAPR.PURPXBHGGURCUBGBF`.

Applying the same operation on it, we get `IUSEDTHEPROGRAMANDHIDITWITH-DUEDILIGENCE.CHECKOUTTHEPHOTOS`

On making it more readable, it will look like this: `I used the program and hid it with - DUEDILIGENCE. Check out the photos`

If we try to look inside the `program.deb` file, we will be able to see that it is actually just the `steghide` program.

If we try to use the `steghide` program to extract all three images using the key `DUEDILIGENCE`, we will get:

```sh
$ steghide extract -sf picture1.bmp -p DUEDILIGENCE
steghide: could not extract any data with that passphrase!
$ steghide extract -sf picture2.bmp -p DUEDILIGENCE
steghide: could not extract any data with that passphrase!
$ steghide extract -sf picture3.bmp -p DUEDILIGENCE
wrote extracted data to "flag.txt".
$ cat flag.txt 
picoCTF{h1dd3n_1n_pLa1n_51GHT_18375919}
```

Hence, the flag will be captured.

## Flag:

```
picoCTF{h1dd3n_1n_pLa1n_51GHT_18375919}
```

## Concepts learnt:

- Basic Wireshark usage
- Basic TFTP
- Basic steghide usage

***

# 2. 

## Description:



## Solution:



## Flag:

```
picoCTF{}
```

## Concepts learnt:

- 

***

# 3. m00nwalk

## Description:

Decode this [message](F/message.wav) from the moon.

## Solution:

In this challenge, we have been given a `.wav` file. If we take a look at the first hint, it says `How did pictures from the moon landing get sent back to Earth?`.

On googling this, we will find out about something called `Slow-Scan Television (SSTV)`. We can then find an online SSTV decoder such as [this](https://sstv-decoder.mathieurenaud.fr/) to decode the `.wav` file.

![SSTV-decoder.png](F/SSTV-decoder.png)

This will give us a `.png` image from where we can see the flag `picoCTF{beep_boop_im_in_space}`.

![decoded-image.png](F/decoded-image.png)

## Flag:

```
picoCTF{beep_boop_im_in_space}
```

## Concepts learnt:

- They used SSTV to transmit the pictures from the moon landing
