# Sudoku

![image](https://user-images.githubusercontent.com/36323843/236673696-b6ab76cf-96c2-46d4-b9fb-86f2f4dc872b.png)

# How to generate a sudoku board.
This algorithm used backtraking algorithm.
```
blanks = position[0..81]
candiates_stack = []
mode = FORWARD
while blank_count == 0:
  nth_blank = candiates_stack.length - 1
  last_pos = blanks[nth_blank - 1]
  next_pos = blanks[nth_blank]
  if mode == FORWARD then
    candiates = get_candiates(blanks[next_pos])
    if candiates is None then
      mode = BACKWARD
    else
      set_number(next_pos, candiates[0]);
      candiates_stack.push(candiates);
    end if
  else if mode == BACKWARD then
     candiates = candiates_stack[last_pos]
     if candiates.length > 1 then
        candiates.removeAt(0);
        set_number(last_pos, candiates[0]);
        mode = FORWARD
     else
        set_number(last_pos, null);
        candiates_stack.pop();
     end if
  end if
```
