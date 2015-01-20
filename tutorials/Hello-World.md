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
