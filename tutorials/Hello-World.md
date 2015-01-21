# Hello World

**Note:** This not done. Not by a long shot.

Based on [this example](http://inventwithpython.com/pygame/chapter2.html)

```Python
import pygame, sys
from pygame.locals import *

pygame.init()
SCREEN = pygame.display.set_mode((400,300))
pygame.display.set_caption("Hello world!")

while True:
   for event in pygame.event.get():
      if event.type == QUIT:
         pygame.quit()
         sys.exit()
      
      pygame.display.update()
```

Actually drawing text on screen.

```Python
import pygame, sys
from pygame.locals import *

pygame.init()
SCREEN = pygame.display.set_mode((400,300))
pygame.display.set_caption("Hello world!")

WHITE = (255, 255, 255)
BLACK = (0, 0, 0)

fontObj = pygame.font.Font(None, 40)
textSurfaceObj = fontObj.render('Hello world!', True, WHITE)

while True:
   for event in pygame.event.get():
      if event.type == QUIT:
         pygame.quit()
         sys.exit()
	 
   SCREEN.fill(BLACK)
   SCREEN.blit(textSurfaceObj, (0,0))
      
   pygame.display.update()

```

Random coloring.

```Python
import pygame, sys, random
from pygame.locals import *

pygame.init()
SCREEN = pygame.display.set_mode((800,600))
pygame.display.set_caption("Hello world!")

WHITE = (255, 255, 255)
BLACK = (0, 0, 0)
RED = (255, 0, 0)
GREEN = (0, 255, 0)
BLUE = (0, 0, 255)

color = WHITE

fontObj = pygame.font.Font(None, 40)

FPS = 60
fpsClock = pygame.time.Clock()
timer = 0
timerLimit = FPS * 3

while True:
   for event in pygame.event.get():
      if event.type == QUIT:
         pygame.quit()
         sys.exit()

   timer += 1
   if timer == timerLimit:
      randnum = random.randint(0, 2)
      if randnum == 0:
	     color = RED
      elif randnum == 1:
	     color = GREEN
      else:
         color = BLUE
         
      timer = 0
   
   SCREEN.fill(BLACK)

   textSurfaceObj = fontObj.render('Hello world!', True, color)
   SCREEN.blit(textSurfaceObj, (0,0))
      
   pygame.display.update()
   fpsClock.tick(FPS)
```
