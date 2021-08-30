Let's say you have the following text in your buffer:

  0. quick
  0. brown
  0. fox
  0. jumped
  0. over
  0. the
  0. lazy
  0. dog

It's a pain to go each one of them and change them accordingly. Until now, I would solve this problem by creating a macro and applying it to the other lines. But there is a better solution. Visually select all of them and press `g<C-a>`. And the list will become:

  1. quick
  2. brown
  3. fox
  4. jumped
  5. over
  6. the
  7. lazy
  8. dog

From the help page:
````
{Visual}g CTRL-A	Add [count] to the number or alphabetic character in
			the highlighted text. If several lines are
		        highlighted, each one will be incremented by an
			additional [count] (so effectively creating a
			[count] incrementing sequence).  {not in Vi}
````
