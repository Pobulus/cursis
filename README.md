# cursis
![tetris](https://github.com/Pobulus/cursis/assets/32367046/160102ec-14ab-4228-95f1-5114d500eb82)

Terminal based tetris game using [ncurses](https://github.com/mirror/ncurses) on Linux or [pdcurses](https://github.com/wmcbrine/PDCurses) on Windows. 

## Compiling with CMake
`cmake . && make`

On Windows you may have to pass the path to your compiler. For example when using MinGW:

`cmake -DCMAKE_CXX_COMPILER=g++ -DCMAKE_C_COMPILER=gcc -G "MinGW Makefiles" .`


## Launching
Simply run the `tetris` executable in your terminal of choice. You can pass these additional arguments at launch:

```
OPTIONS:
 -k <filename> 	to use custom keybinds specified in a file
 -h     	display this help message
 -t <0-4>       set theme
```
## Gameplay
![tetris gameplay](https://github.com/Pobulus/cursis/assets/32367046/9585d4fc-8cfd-408f-b404-512aaf83e4bb)
### Game modes
This game features 4 game modes:
1. **Classic**: arrange the falling blocks into horizontal lines to clear the playing field
2. **UpsideDown**: like classic but with gravity flipped
3. **Shaky**: goal stays the same but block can randomly move left or right while falling so you have to be cautious
4. **Infection**: normal rules apply but:
    - _red_ tiles are healthy and if there are no red tiles left on the field you lose the game
    - _green_ tiles infect neighouring red tiles on every block drop
    - _blue_ tiles are immune and can be used to seperate greens from reds

### UI elements
- **Level** - determines how fast the blocks drop i.e. the game difficulty
- **To LvlUp** - how many lines you must clear to increase your level
- **Score** - scoring is based on how many lines you clear in one drop and the level
- **Hold** - currently held block. Can be swapped once per drop
- **Next** - the next block in the queue

This game features _ghost block_: differently textured copy of the current block showing where it would be when dropped

### Controls 
> These are the default setting, you may choose to create you own config via the controls option in main menu
- `A/D` - move the block left/right
- `Q/E` - rotate the block left/right
- `S` - lower the block by one tile (Soft Drop)
- `<spacebar>`- drop the block all the way down (Hard Drop)
- `F` - hold the block (swap with hold slot)
- `P` - pause
- `<esc>` - forfeit the game/exit from main menu
 
 
