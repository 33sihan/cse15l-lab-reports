# Part One
I pick changing the name of the start parameter and its uses to base.

---
The sequence of keys: `/start<Enter>dwibase<Erc>ndwibase<Erc>ndwibase<Erc>n:wq<Enter>`

Step 1: type `/start<Enter>`

Description: to search the word *start* in this file and the cursor jumping to the first *start* word

![](searchStart.png)


Step 2: type `dw` 

Description: to delete the word where the cursor is at.

![](dw.png)


Step 3: type `i`

Description: to enter the insert mode 

![](insertMode.png)


Step 4: type `base<Erc>`

Description: insert the word *base* and use <Erc> to go back to the normal mode
  
![](baseNormalMode.png)


Step 5: type `n`

Description: search forwards for the next occurrence of word *start* and move the cursor to the beginning of the word
  
![](nextStartWord.png)

Step 6: type `dw` 
  
Description: to delete the word where the cursor is at.
  
![](dw2.png)

Step 7: type `i`
  
Description: to enter the insert mode 
  
![](inserMode2.png)

Step 8: type `base<Erc>`
  
Description: insert the word *base* and use <Erc> to go back to the normal mode
  
![](baseNormalMode2.png)

Step 9: type `n`
  
Description: search forwards for the next occurrence of word *start* and move the cursor to the beginning of the word
  
![](nextStartWord2.png)

Step 10: type `dw` 
  
Description: to delete the word where the cursor is at.
  
![](dw3.png)

Step 11: type `i`
  
Description: to enter the insert mode 
  
![](inserMode3.png)

Step 12: type `base<Erc>`
  
Description: insert the word *base* and use <Erc> to go back to the normal mode
  
![](baseNormalMode3.png)

Step 13: type `n`
  
Description: search forwards for the next occurrence of word *start* and move the cursor to the beginning of the word,  
and then we can find the next word named "start" is not the parameter that we want to change and it is the last word named "start"
  
![](nextStartWord3.png)

Step 14: type `:wq<Enter>`
  
Description: to exit vim and save changes we just made
  
![](wqSave.png)

# Part two
In this part, I test the time of editing and running the file HelloWorld.java in two different ways.
For the first option, I spent about 58 seconds. And for the second option, I spent about 75 seconds.

Answer for question 1:
I prefer vim although I am still not really familiar with how to use it.
However, after mastering it, I believe it is faster than editing on local and scp the file to remote since vim needs fewer steps. And vim can allow us not need to switch from local to remote again and again.

Answer for question 2:
Actually, I believe the project may factor most people and make them prefer editing on local since we are still not familiar enough with vim.
