##### What does a space on the tak board contain?
A stack (LIFO or FIFO depending on situation) of game pieces
    There are 2 types of pieces - the capstone and the road/wall
        The road/wall tile has 2 configurations.
            Walls can only exist at the top of the stack.
        The capstone can also only be at the top of the stack and will convert any wall it lands on into a road
    The pieces in a given stack can belong to either team
    
##### What actions can clicking on an empty space trigger?
Place a road tile.
    Add a road tile to the stack
    Give control to whoever placed the tile
Place a wall
    Add a wall tile to the stack
    Give control to whoever placed the tile
Place a capstone
    Add a capstone piece to the stack
    Give control to whoever placed the tile

##### What actions can clicking on stack trigger?
1. Pick up to as many pieces (LIFO) as board dimensions (so 3x3 -> 3 pieces max)
    EX: Player could pick up 4 out of the 5 pieces at B3
       1 2 3 4
    a [0,0,0,0]
    b [0,0,5,0]
    c [0,0,0,0]
    d [0,0,0,0]
2. Move a number of spaces (Minimum 1, Maximum - Pieces in hand || Hit the edge of the board) in a straight line
3. Must leave behind at least 1 tile for each space moved after the 1st. Tiles left behind are selected in FIFO order.
    EX: Valid progression from last example board
       1 2 3 4
    a [0,0,0,0]
    b [3,1,1,0]
    c [0,0,0,0]
    d [0,0,0,0]
    EX: Invalid progressions from last example board (each showing a bad state 1 turn after original)
       1 2 3 4     1 2 3 4     1 2 3 4
    a [0,0,0,0] a [0,0,0,0] a [0,0,0,0]
    b [4,0,1,0] b [4,1,0,0] b [0,1,1,0]
    c [0,0,0,0] c [0,0,0,0] c [2,1,0,0]
    d [0,0,0,0] d [0,0,0,0] d [0,0,0,0]
4. Move ends when no tiles are left in hand or the edge of the board is reached.

##### What other movement limitations are there?
Roads and Walls can only 'capture' Roads
Capstone can move on to Roads or Walls. Roads are captured while Walls are converted into Roads
Nothing can be placed on top of a Capstone


