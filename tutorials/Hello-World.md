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
