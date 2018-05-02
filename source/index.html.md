---
title: API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - java
  - maml

toc_footers:
  - <a href='https://github.com/lord/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true
---

#What is Maml?
Maml is a set of letters and numbers that make it easier to interface with MIDI.
Pellet feed is a set of words otherwise known as a Sentence. A word is a set of notes and beats separated by // and also a set of letters that can describe notes and beats . 
a word can also be an actual word. 
>type  '' Hello World '' 

## Making music via keyboard
1. Check "Use Keyboard for Input" is selected/on
2. Play notes 
3. Press "Save Maml Buffer" when you have a phrase.
4. Press "Render in Maml"

## Make words from keyboard
1. Check "Use Keyboard for Input" is selected/on
2. Play notes 
3. Press "Save Maml Buffer" when you have a phrase.
4. Put your word before the equals sign

> type in Maml Buffer:  myWord=abcdefg//8,8, myWord myWord
5. Press "Render in Maml"

## Make a variation of Twinkle Twinkle Little Star 
1. Turn off "Use Keyboard for Input"
2. Paste twinkle code into Maml Buffer (it has a blue border)
3. Press Render in Maml
> twinkle=4c,4c,4g,4g,4a,4a,4g,//8,8,8,8,8,8,(4,8,),
uppa=4ggffeed//AAA(4,8,),
HowIWonder=4f,4f,4e,4e,4d,4d,4c,//8,8_,8,8_,8,8_,(4,8,),
twinkle HowIWonder uppa uppa twinkle HowIWonder


<aside class="warning">MAML is awesome!</aside>
## For typing in notes and beats manually
```Maml
You can add beats to your notes. 
P is a quarter note (pie)
A is two eighths (Apple)
H is four sixteenths (Huckleberry)
L is 3 thirds (Lemonade)
```
```Maml
You can add beats to your notes. 
4 is a quarter note 
8 is an eighth note
16 is a sixteenth note
12 is 1/3 of a triplet 
```

( see the pie game for more information)
[Pie Game]( "http://www.tanglewoodmsband.org/uploads/1/7/9/6/17968915/pie_game.pdf")
>type '' helloo//PAPA ''

notes can also be inserted, the octaves split is on c, default octave is 3.

>type '' 4cdefgab5cdefgab6c//P '' 

it puts a quarter note on each of the notes. The beats are in a modulo of size, so if the beats are less than the notes, then the beat picker loops over and plays the next note in the loop.   

##Beats
Beats can be a number next to a comma or a named group of numbers:
>type '' aaaaa//8,16,12,7 ''

this plays a 5 times, with an 8th, a 16th, a 12th , and a 7th note.

##Rests
rests can be on notes or beats after the note or beat. 

>type '' 4c_defgab5c//8,4,8,4,8,4,8,4,8, ''

>this rests a 8th note, and then plays the rest of the notes. It turns the notes off, but keep the beat there. 

##Sharps and Flats
Sharps are '#', flats are '@' and come before the note. '#c' is a c sharp, #c_ is a rest note. 

>type cfl@t#harp//8,8,16,16, 

<aside class="aside">Horrah! MAML is awesome!</aside>  



