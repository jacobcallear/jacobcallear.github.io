---
img-grid:
  src: raspberry-pi-logo.jpg
  alt: Raspberry Pi logo
category: Video Game
github-repo: jacobcallear/sense_hat_plus
languages: Python
summary:
  Adds features to the Raspberry Pi Sense HAT. Can play the snake game on the
  8x8 LED grid.
---

### Code Samples

`Python`: Initialising the `SnakeHat` class to describe the pixels for the snake
game

```python
class SnakeHat(SenseHat):
    '''Describes the 8x8 LED grid for a snake game.'''

    def __init__(self):
        super().__init__()
        # Light pixels
        self.clear()
        snake_pixel = self.set_random_pixel(colour=(255, 0, 0))
        # Describe position of snake on LED grid
        self.snake = deque([snake_pixel])
        self.free_coords = {
            (x, y)
            for x in range(8)
            for y in range(8)
        }
        self.food_on_board = False
        self.food_coord = None
```
