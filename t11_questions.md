# T11: The Legend of Tuna: Breath of the Catnip

## Instructions

Please replace each `**Replace This Text With Your Response**` with your answer.

___

## SECTION 1

1.a. First, discuss with your team and assign yourselves roles. Try to pick the role you’ve had the least experience in.

```
    |                 | Monday | Wednesday | Friday |
    |-----------------|--------|-----------|--------|
    | Driver          |   Meg  |  Mag      | Meg    |
    | Navigator       |     Mag|   Meg     |  Mag   |
    | Quality Control |        |           |        |
```

___

## SECTION 2

2.a. Look at the three Python files in the repository. Identify below all of the classes, and a brief description of
    what each one represents:

```
    For the Game class it is defining the game logic. While NPC class defines what a 'good npc' and controls its movement.
    Last the class player represents the player and controls it's movements.
```

2.b. Look more closely at the **t11_game.py** file. There are 8 lines; identify if they are 
    a) instance parameters
    b) method calls within the class
    c) method calls to another class or library

(Some are more than one answer!)

```
    self.size = 800, 600                              # A
    self.running = True                               # A
    pygame.init()                                     # C
    self.screen = pygame.display.set_mode(self.size)  # C
    self.clock = pygame.time.Clock()                  # C
    self.player = Player(self.size)                   # C
    self.good_npc = NPC(self.size)                    # C
    self.screen.fill('#9CBEBA')                       # A
```

2.c. Parse through the `run()` method of **t11_game.py**. In particular, note how the game handles 
    a) collisions between the player and NPC,
    b) moving the player and NPC around the screen, 
    c) redrawing the player and NPC after they move,
    d) how often the game updates the screen

In your own words, describe how the four items above are accomplished in the Game class:

```
    a) It checks to see if the stament is false and prints "Taco you caught me" it ends the game. 
    b) The program moves the player based of the keys pressed by the user, while the NPC is based off of a random selection of n, e, s, w.
    c) This is done through the .blit method which allows the program to erase the current object and redrawing the new updated object.
    d) This is done through the self.clock.tick method that assures it updates 24 times a second.
```

_Return to the Google Doc to continue the assignment._

---

## SECTION 3

3.a: Take a look at the **t11_player.py** file. What class does the `Player` class inherit functionality from? 
     How do you know?

```
    The 'Player' class inherits its functionality from the 'Sprite class in pygame'. We know this because the 'Sprite' class was passed in to the 'Player' class as a parameter
```

3.b. Sprites need two attributes to function: A surface and a rectangle. The surface (implemented in a `Surface` 
     class inside **pygame**) represents the drawing that will be rendered to the screen. The rectangle 
     (implemented in the `Rect` class in **pygame**) represents the area where the surface will be drawn on the screen, 
     including its width, height, and position. Find the lines of code that implement these two ideas, 
     and explain what each line does. 

```
    For the player, the code the implements this is Line 32-35, while for NPC it is Line 34-37.
```

3.c. The `Player` class has only one method so far. Parse that code and docstring, and describe what it does:

```
    This method listens for the keypress from the user and depending on what the keypress is (up, down, left, right), it moves the player 3 pixels in the respective direction.
```

3.d. Similarly, the `NPC` class in **t11_NPC.py** also inherits the `Sprite` class from **pygame**, 
     but it does a little more than our `Player` class. Compare the two classes, and identify/describe the differences:

```
    The NPC Class has a random path that it follows and also starts its position in the middle of the screen.
```

3.e. Of particular interest is how we keep the `NPC` on the screen. Describe how we're using 
    the `self.rect` attribute in the `get_direction()` method to keep the `NPC` visible.  

```
    As the 'self.rect' goes past the boudnaries of the screen size, the 'self.path' attribute is changed to the opposite direction to ensure the NPC stays on screen.
```

_Return to the Google doc to continue the assignment._ 

---

## SECTION 4

Using **t11_NPC.py** as a starting point, create a new class called `Good_NPC` (you can do this in the **t11_NPC.py** 
file, or create a new file; your choice). Have the new class inherit from the `NPC` class that I gave you, 
including calling the parent class's initializer. Convert **t11_game.py** so that it spawns Taco Cat as a `Good_NPC` 
instead of an NPC. Debug any errors you get; the program should work, at this point. 

4.a. How hard was it to create the child class, given the parent?

```
    It was challenging to figure out which parameters were needed in the child class.
```

The parent class `NPC` currently holds attributes like the image used, which are actually more specific to 
`Good_NPC` now. Refactor the code so that you can indicate the image for Good_NPCs and Evil NPCs (coming next)
inside the child classes, instead of the parent class. There are multiple ways to accomplish this; discuss with your 
partner first how you would like to approach this problem. 

Next, implement another new class called `Bad_NPC` (again, you can do this in the **t11_NPC.py** 
file, or create a new file; your choice). Our bad NPC (Whiskers) is going to march around the screen in a different way
than our friend Taco Cat; he should move like a Boustrophedon, working his way across the entire screen, before 
moving up or down. Because this NPCs movement is significantly different from the Good NPCs movement, we should 
make a design choice. We could:
    a) keep the `movement` method in NPC, and override it inside `Bad_NPC` with a new method.
    b) remove `movement` from NPC, and implement separate `movement` functions in each child class.
    c) refactor `movement` in NPC, so it can handle both child class options.

4.b. Discuss with your partner your design choice above, including their pros and cons. Document your 
     choice and why: 

```
    We chose 'B' because we figured it would be less complicated to create the code separately for both child classes.
```

Finally, we need to create our enemy object, Whiskers. Update **t11_game.py** to:
    a) spawn `whiskers` at the beginning of the game
    b) make `whiskers` move around the screen
    c) handle collisions between Tuna and Whiskers, which ends the game
    d) (optional) handle collisions between Taco Cat and Whiskers, which kills Whiskers and spawns a new evil NPC

---

## SECTION 5

5.a. Inheritance allows us to produce special cases of a class, extending their functionality. Describe
    what challenges you faced while implementing the child classes that extended the `NPC` class. 
    How did you overcome them?

```
    **Replace This Text With Your Response**
```