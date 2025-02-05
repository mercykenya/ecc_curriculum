---
layout: layouts/activity.njk
tags: learn
category: Tutorial
title: "5 Uses of For Loops"
description: Learn five different ways to use for-loops in Python to make music.
authors: by Anna Xiao 
level: Intermediate
time: 20-30 mins
license: by-nc-sa
splash: /images/splash/for-loops-splash.png
project: https://tunepad.com/project/76552
audio: https://api.tunepad.com/api/projects/76552/audio/
---

# Step 1: Create a new Project
Log in and create a new TunePad project at [tunepad.com](https://tunepad.com). Name your project “5 Uses of For Loops”.

# Part 1: Basic usage of for loops 
We’ll start with one of the most basic usage of a for loop, where you iterate over the elements of a sequence (e.g., a list, tuple, or string). The loop variable takes on the value of each element in the sequence, one by one, allowing you to perform operations on each element.  

Start by declaring some note variables and use this to make a melody list:

```python
C = 60
D = 62
E = 64
F = 65
G = 67
A = 69
B = 71

melody = [C, D, E, F, G, A, B]
```

Now we use a for loop to play each note in the melody
```python
for note in melody:
    playNote(note)
```
The first line starts the for loop. It says, "For each element (in this case, each note) in the melody list, do the following:"

Essentially, we are calling the playNote() function for each of the notes in the melody list. We replace note with the corresponding element in the melody list.

# Part 2: range():
Next, we will try working with range(). The range() function is often used with for loops to generate a sequence of numbers. It can be used to iterate a specific number of times or to generate a range of numbers within a certain interval. This is particularly useful when you need to perform a task a fixed number of times or work with numerical sequences.


Use this code for your drone sound:
```python
for i in range(60, 72):  
    playNote(i)
    rest(0.5) 
```

The range(60, 72) function creates a list from 60 to 71 (up to, but not including, 72).
We are calling the playNote() function for each of the notes from 60 to 71, and replace i with the corresponding element from the list generated by range(). And we play a short rest of 0.5 beats after each note is played.

# Part 3: Nested For loops
Nested for loops occur when you have one for loop inside another. The inner loop is executed for each iteration of the outer loop. 

First, let's create have a list called chords containing three sublists. Each sublist represents a chord, and each element within the sublist represents a note in that chord.
```python
chords = [[C, E, G], [D, F, A], [E, G, B]]
```

Here is how a nested for loop can be used:
```python
for chord in chords:
    for note in chord:
        playNote(note)
    rest() 
```

The outer loop starts by assigning the first sublist [C, E, G] to the chord variable. The inner loop starts, and note takes on the values inside the first cord. Once this first chord is finished playing, the rest() function is called. 

The inner loop has completed all iterations for the current chord, so the outer loop moves to the next sublist. And the inner loops moves through all the iterations for this next chord. 

The process repeats for the third chord. After all chords have been iterated through, the nested loop ends.

# Part 4: Loops with conditional statements 

Within a for loop, you can use conditional statements (e.g., if, elif, else) to control the flow of execution. 

Try declaring a list and making a for list with the following conditionals:
```python
melody = [C,C,G,G,A,A,G,B,F,F,E,E,D,D,G,B,G,G,F,F,E,E,D,B,G,G,F,F,E,E,D]
         
for note in melody:
    if note == B:
        rest()
    else:
        playNote(note, 0.5)

```

We are looping over the elements in the melody list again. However, this time we are adding conditional statements within the for loop. This means we are selectively executing code based on certain conditions. 

In this example, if the element is a B note, we call rest(). Otherwise, we call playNote() with that note element. 

# Part 5: Loops with conditional statements 

The enumerate() function is used to iterate over a sequence while also tracking the index or position of each element. It returns a tuple containing the index (or a custom counter) and the corresponding element from the sequence.

Create 2 lists:
```python
melody = [C, D, E, F, G, A, B]
durations = [0.5, 0.75, 1, 0.5, 0.25, 2, 1] 
```

These lines create two lists: melody and durations. The melody list contains the notes (C, D, E, F, G, A, B) that make up the melody, and the durations list contains the corresponding duration values (in some unit, e.g., beats) for each note.

Now try this:
```python
for i, note in enumerate(melody):
    #print(i, note)
    playNote(note, beats = durations[i])
```

The enumerate(melody) function returns an enumerate object that produces tuples containing the index and the corresponding element from the melody list. The loop variables i and note will take on these values in each iteration.

Within each iteration, we have a call to playNote() like this:
```python
playNote(note, beats=durations[i])
```

This will play the current note from the melody list, and the beats argument will be set to the corresponding duration value from the durations list. If it helps you, you can print the values of i and note within the for loop to better visualize what they are. 

In the first iteration: i will be assigned the index 0, and note will be assigned the first element of melody, which is C, and playNote(C, beats=durations[0]) is called, which plays the note C with a duration of 0.5 beats (since durations[0] is 0.5).

This pattern continues until all elements in melody have been iterated through.

# Try It
Open this project in TunePad <a href="{{project}}" target="_blank">{{ project }}</a>
