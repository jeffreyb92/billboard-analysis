# Analysis of the Billboard Top 100 Songs from 1964-2015 

I found this dataset not too long ago, and when I went to check it out I had some questions.

First, I was curious about who had been in the Top 100 Billboard songs the most.
Then, I took that same question and applied it to each decade.
Following that, I then got curious as to what were the most common words used in a song on the Top 100 Billboard songs for all these years? What about in the 60's? 70's? 80's? etc.
So I took all these questions, and this is what I found.

    To answer the first question, I made a for loop that would take each artist and insert them into a dictionary, along with a count of how many times they appeared on the Billboard Top 100. If they showed up more than once, we added to the number that is in the dictionary. Then, I used a max function to pull out which value was the highest in the dictionary. 

    Now, because I didn't know what to expect here and how many artists would show up how many times, I made a for loop that went through the dictionary and every time the max highest value showed up, it would print out that artists name. After running this loop, I found that Madonna was the only artist that had been on the Billboard Top 100 for a total of 35 times.

After I found that out, I was curious to see how many people had been on the Billboard Top 100 more than 10 times, theorizing that if they are to be well-known artists then they would probably have been on it multiple times. So I wrote a dictionary comprehension (like a for loop but in one line of code) to loop the dictionary I just made and set a value that had to be equal or greater than 10 in order to make the cut.