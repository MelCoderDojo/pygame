# Simple Movement

**Note:** This is not finished yet.

```Python
import pygame, sys, random
from pygame.locals import *

pygame.init()
SCREEN = pygame.display.set_mode((800,600))
pygame.display.set_caption("Boxes")

WHITE = (255, 255, 255)
BLACK = (0, 0, 0)
RED = (255, 0, 0)
GREEN = (0, 255, 0)
BLUE = (0, 0, 255)

ticks = deltaTime = getTicksLastFrame = 0

box1 = {
   'rect': pygame.Rect(50, 50, 50, 50),
   'color': RED
   }

box2 = {
   'rect': pygame.Rect(200, 200, 50, 50),
   'color': GREEN
   }

while True:
   for event in pygame.event.get():
      if event.type == QUIT:
         pygame.quit()
         sys.exit()

   keys = pygame.key.get_pressed()
   movement = round(300 * deltaTime)
   
   if keys[K_LEFT]:
	   box1['rect'].x -= movement
   if keys[K_RIGHT]:
	   box1['rect'].x += movement
   if keys[K_UP]:
	   box1['rect'].y -= movement
   if keys[K_DOWN]:
	   box1['rect'].y += movement

   SCREEN.fill(BLACK)

   pygame.draw.rect(SCREEN, box1['color'], box1['rect'])
   pygame.draw.rect(SCREEN, box2['color'], box2['rect'])
      
   pygame.display.update()
   
   # Get deltaTime in seconds
   ticks = pygame.time.get_ticks() / 1000.0
   deltaTime = 1.0 * (ticks - getTicksLastFrame)
   getTicksLastFrame = ticks
```
