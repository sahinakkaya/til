Most "modern" text editors stores only one undo branch. That means, if you go back in the history and change something, you can't redo. You probably didn't even think about *why* it works this way because all the programs you are using (including the ones that are not for editing text) works like this and you take it for granted. But man, come on we are living in 21st century all we wanted to do is edit some text. It shouldn't be this hard. 

If you understand the problem, I will say Vim for the rescue! Press `g-` or `g+` to go older or newer states in your history. Normal `u` and `C-r` will make you travel your history in a linear way but `g-` and `g+` will show you all possible states. 

Now, forget whatever you are doing and switch to vim.
