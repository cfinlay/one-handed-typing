Many people type with only one hand, myself included. These are my collected thoughts and
notes on typing with one hand, which I've gathered since I lost the use of my left
hand several years ago.

## To QWERTY or not to QWERTY
Initially I thought I'd just relearn to type one-handed on a standard US QWERTY
keyboard. This approach is appealingly simple. No custom configuration files,
no special hardware, no need to mess with settings on every computer you interact with.

Ultimately though, I gave up on this approach after about a year. QWERTY is a
horrible layout to begin with, and typing on it with only one hand is even more
terrible. On a standard QWERTY keyboard, one handed typists must move their
wrist horizontally left and right to access many common keys. The repetitive
strain of this movement takes its toll, and after each work day of typing, I
was coming home with a lot of pain in my wrist. Needless to say, when you only
have one good hand, this is something to be avoided at all costs.

## Solutions
There are a quite a few solutions out there. These are the ones I considered
before settling on a Dvorak one handed keyboard layout, plus a few extra modifications.

### Mirrorboard
The first I considered is [xkcd's
mirrorboard](https://blog.xkcd.com/2007/08/14/mirrorboard-a-one-handed-keyboard-layout-for-the-lazy/),
which reflects one half of the keyboard onto the other half whenever a modifier
key is active. There are 'smart' commercial versions of mirrorboard available
as well, which use predictive text to eliminate the need for a modifier key.
However, I decided not to go with this approach. To me it seemed like a half
measure: why relearn how to type on half a QWERTY keyboard when there are
keyboard's specifically designed for one handed typing?

### Chorded keyboards
Another approach would be to learn to type on a [chorded
keyboard](https://en.wikipedia.org/wiki/Chorded_keyboard), in which one chord
of key combinations maps to a particular letter. This yields a vast decrease in
the number of keys needed. There are commercial devices available, including
Frogpad (which seems to now be defunct) and the
[Twiddler](https://twiddler.tekgear.com/).

Although I'm was intrigued by this
approach, and maybe one day I'll give it a go, it seemed pretty hardcore. Maybe
a wearable tech enthusiast will one day change my mind, but I wanted a tweak
to my typing setup, not a whole new approach.

### Speech-to-text software
Many people suggested I try speech-to-text software, like [Dragon Naturally Speaking](https://www.nuance.com/dragon.html). I think this could work for most tasks, like writing documents or emails. I was dissuaded though by two items. First, I'm a Linux user, and as much as I like FLOSS, there doesn't really seem to be any competitive alternatives to Dragon Naturally Speaking for Linux. Second, most of my workdays are spent coding, and the idea of coding by speech was daunting.

### Dvorak to the rescue
In the end I went with the right handed variant of the [Dvorak keyboard
layout](https://en.wikipedia.org/wiki/Dvorak_Simplified_Keyboard#One-handed_versions).
This layout is available on all operating systems. So switching is simple: it's just a matter of
opening your computer's keyboard preferences and choosing the Dvorak one handed
layout. This fact alone is a big selling point, any computer can be easily
switched trivially, no matter if the computer is yours, or if you're using it
for five minutes.

The history of the one handed layout is relevant here. There's a lot of
rumour and myths about the original Dvorak layout and its merits, depending on
your proclivities. However, the one handed layouts were created in the late
1940s. After [Colonel Robert
Allen](https://en.wikipedia.org/wiki/Robert_S._Allen) lost his right arm in the
Second World War, he contacted [August
Dvorak](https://en.wikipedia.org/wiki/August_Dvorak) to create a one handed
keyboard layoutr. Dvorak used the same methodology to design the one handed
variants as his original layout. So, at least there's a method underscoring the
one handed layouts!

The layout is designed to minimize horizontal motions, the motions which were
giving me wrist pain. The most frequent letters in English are all accessible
either from the home row, or one key away.  It's a much more pleasent
typing experience, all told.

## Physical modifications
Having settled on the Dvorak one handed layout, it's time to make some changes.
Without physically altering the keyboard, it'd be pretty hard to learn the
new layout, since you wouldn't be able to see what keys you're typing. Of course,
the long term goal should be touch typing, without looking down at the keys.
But to learn, and say for precision typing like entering passwords, it'd be
nice if keys match letters.

Physically swapping keys is not hard, if proper care is taken. Most laptop
keyboards use a scissor type mechanism to hold the key in place. You can pop
off the key with a flat head screw driver, by carefully sliding the head of the
screw driver under a __top corner__ of the key and carefully prying it. Do
not lift from the bottom, you'll break the scissor. Once you've popped off all
the keys, just rearrange them to your layout, and you're good to go.

The way you pop off the keys depends on the [type of keyboard
mechanism](https://en.wikipedia.org/wiki/Keyboard_technology) in your keyboard.
I've only ever dealt with scissor keyboards and spring keyboards. Scissor
keyboards are a bit tricky, while spring keyboards are bomb proof.

## Touch typing
Become a one handed touch typist is not hard on with a Dvorak one handed
keyboard. All the most frequent keys are within one key of the home row.  On a
right handed layout, the home row is `EHTD`; on the left handed variant it's
`DTHE`.  Notice how typing 'the' is only one roll!

It took me about a month to learn to touch type on the new layout. My work
involves a lot of typing, so it may take longer if you're not spending hours at
a time on a keyboard. But with a bit of dedicated practice, it's totally
doable.

I now pretty consistently touch type at around 45 wpm, which is not so bad.
I've heard that the average two handed touch typist has a typing speed of about 58
wpm; while the average typist (hunt and peck, and it's variants) clocks in at
around 36 wpm.

## Extras modifications for periphery keys
For most typing, a one handed keyboard layout is almost all you need. I found
however that even with this layout, with the common keys arranged vertically, I was
still making many horizontal left-right motions for non-letter keys. For
example, capital letters requires simultaneous activation of the `Shift` key,
and the letter in quetion.  For some letters, this leads to contorting your
hand into strange and unnatural shapes.  Furthermore, the keys `Tab`, `Esc`,
`Backspace` and `Enter` are all placed near the periphery of the keyboard.
Especially when writing code, these keys all contribute to unwanted horizontal
left-right motions.

Here are my solutions to the periphery keys problem.

### Foot switch for `Shift`
I remapped a cheap USB foot switch to function as a `Shift` key, eliminating
the need for simultaneous key presses every time I need to type a capital
letter.

You can buy USB foot switches for very cheap, under $10 on Amazon. A couple
years ago I bought a box of FS1-P foot switches for something like $50. I keep
a foot switch at home, at the office, one in my backpack, on the patio, at the
pub, in my car. Everywhere you might need to `Shift` gears.

Every operating system has a way to remap input key codes, like the one
generated by a foot switch. I've included a description for each operating system in the subfolders here, with example code if necessary.

### Function keys
When was the last time you actually used function keys `F5` through `F8`?
Probably never. Talk about useless. These keys are also conveniently located
directly atop the home row of the one handed keyboard! Candidates for
reassignment? I think so.

To eliminate horizontal motions, I remapped `F5` to `Tab`; `F6` to `Esc`; `F7`
to `Backspace`; and `F8` to `Enter`. I've put the details on how to do this for each operating
system in a subfolder here.

With this remapping, and a foot switch for `Shift`, I've found that nearly all
horizontal motions have been eliminated.
