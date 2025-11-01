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

- 

***

# 3. Bare Metal Alchemist

## Description:

my friend recommended me this anime but i think i've heard a wrong name.

## Solution:



## Flag:

```
picoCTF{}
```

## Concepts learnt:

- 
