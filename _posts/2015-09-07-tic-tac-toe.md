---
layout: post
title: Tic Tac Toe
date: 2015-09-07
---

It's 5 hours in on a 7 hour plane flight. The stale airplane coffee air
is beginning to make me nauseous, I can't sleep, and the movie selection
on the plane is beyond terrible. I look over to my grandmother with
pleading a smile, and bless her, she returns it. "Do you want to play a
game with Grandma?" she asks sincerely. A toothy grin ripples across my
face as I nod. "Alright." she offers. She's doubled over, feeling around
a fake Louis Vuitton for something, gently, with only the grace that a
grandmother can manage, she extracts two pens and a folded piece paper
from the leathery bag. She places the paper on her tray table and makes
a small grid, handing me a pen she asks with the slightest hint of
mystery, "Do you know how to play TicTacToe?". The plane lands.
Grandma's sheet is covered in TicTacToe boards, there's a tally at the
top of the page. G: 13, J: 0.

20 or so years later and I'm sitting at my living room table bent over
my favorite oversized notebook, there's a slight breeze coming in from
the open window that brings with it traces of the street din below. the
sun is starting to set and my mind is racing. "How do I build an
unbeatable TicTacToe game?" I wish I could say my Grandmother was coming
to visit and that I finally wanted to beat her after all these years,
that would tie everything together nicely, and I'm not that gifted in
storytelling.

The truth is, my friend Abi introduced me to Kevin a software craftsman
at 8th Light. 8th light is unique. They have an apprenticeship program
that they promote above almost anything else and they call their
developers software craftsman. For someone that's interested in crossing
the chasm of suck, i.e (my code sucks and I want to make it suck less) a
culture predicated on mentorship and taking pride in one's work sounded
like the perfect fit.

Kevin happened to be looking for an apprentice and suggested I work on
this TicTacToe game in advance of a paired coding session on Friday. I
took paired coding session to mean informal technical interview and
spent the next 3 days and nights working my ass off to make an
impression. Luckily, I think it worked. After our paired session Friday,
I was offered the 8th Light student apprenticeship.

That brings us back to Tuesday night. Here's what I wrote:

**Create a game of TicTacToe to be played in the command line.**

1.  first we need two players 1 human, 1 computer
2.  we need a way to start the game
3.  next we need to draw the board.
4.  then we need to have a system to populate the board. i.e what do we
    select
5.  then we need a way to add Xs and Os to the board.
6.  an interface to tell us what the computer selected and asking us to
    select a tile
7.  we need a way to keep a tally of which pieces on the board are left
8.  we need a way to determine a tie or a winner.
9.  we need to build an ai that never loses

Who would have thought there's so much that goes into building a simple
game! I've also learned from doing the Project Euler problems that
translating English into code is not a trivial thing, but it provided a
starting point. so I got started.

It seemed clear that I would need a Game class since TicTacToe is a
game. The first thing I did was figure out how to make a board object. I
tinkered with a Board class for a while before deciding to build a BOARD
constant hash of key value pairs 1-9 they key being an integer and the
value a string of the integer (1 for each spot on the board). I went
with a constant instead of a class because at this point that was the
only way I could think of to have the BOARD be accessible to all the
different methods that needed it. In the Game class I decided to have
the instance variables @human, @computer, @player\_1, @player\_2 because
I thought that this would satisfy the first condition I laid out to have
an unbeatable game. I knew less about instance variables than I thought,
and this strategy didn't quite pan out. I still was able to make methods
for a human and com[Publish](https://buttercms.com/post/tictactoe#)puter
player within the class, which effectively satisfied the condition for
\#1. At this point I had done 1-4 it was 3 or 4 am and I needed to
sleep.

The following day I set out allowing for the player to select whether
he/she wanted to go first or second. that added functionality was not
necessary for the challenge, but I thought it added enough to the user
experience that it was worth including. From there I went about adding a
Human and Computer class since my instance variables in the Game class
were not cutting it. I made the logic better for the computer and moved
the BOARD constant to stand alone outside of any class I also changed
the values of the hash to integers, which made the logic for the
computer moves work much better.

Figuring out how to declare a winner came with its own challenges,
mostly self-conceived. I really wanted to come up with an extremely DRY
way to check for a winner, and ended up wasting a lot of time on this
and not really getting anywhere until I wrote the uglier code and
refactored later. A lesson I'll remember: it pays to be lazy in coding.
Or at least it makes more sense to write something you know will work
and go figure out how to make it better later.

The most difficult part was figuring out the logic to make the computer
unbeatable. I don't think I ever did, but I do think I got pretty close.
I created an array of arrays that contained the winning combinations. I
then created 2 empty arrays that I called human moves and computer
moves. Whenever the human player made a move it would push their move to
the human move array - same with the computer. I then looped through the
winning combinations array to find all the arrays where either the last
move of the computer and the last move of the human player shared a
combination. Or the two last moves of the human player shared a
combination. I pushed that into a new array and then eliminated all of
the moves that had already been played by subtracting this new array by
the human and computer moves array. This new array now contained all the
available and smart moves for the computer to choose. I sampled that
array to provide a value for my computer move logic and voila!

At this point I thought I had completed all of the challenge, but was
still not happy with the organization of my code. I first figured out
how to refactor my ugly win checking logic, and then set my sights on
revamping my domain structure, which of course broke everything. When
Friday rolled around, I had tinkered to the point that the game no
longer worked, but I was confident I could explain where I was headed
and hopefully get some feedback. I already told you what happened.

Writing this I realize it would be much more helpful if I didn't do it
in retrospect. As I start my apprenticeship and continue to build on the
TicTacToe gameI will be sure to explain my thinking as I go.
