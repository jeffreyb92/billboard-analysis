# Analysis of the Billboard Top 100 Songs from 1964-2015 

I found this dataset not too long ago, and when I went to check it out I had some questions.

- First, I was curious about who had been in the Top 100 Billboard songs the most.
- Then, I took that same question and applied it to each decade.
- Following that, I then got curious as to what were the most common words used in a song on the Top 100 Billboard songs for all these years? What about in the 60's? 70's? 80's? etc.\s\s
So I took all these questions, and this is what I found.

## Part 1: The Top Artist of ALL TIME

To answer the first question, I made a for loop that would take each artist and insert them into a dictionary, along with a count of how many times they appeared on the Billboard Top 100. If they showed up more than once, we added to the number that is in the dictionary. Then, I used a max function to pull out which value was the highest in the dictionary. 

Now, because I didn't know what to expect here and how many artists would show up how many times, I made a for loop that went through the dictionary and every time the max highest value showed up, it would print out that artists name. After running this loop, I found that __Madonna__ was the only artist that had been on the Billboard Top 100 for a total of 35 times.

### Part 1a: Artists with 10 or more Top 100 Hits
--- 
After I found that out, I was curious to see how many people had been on the Billboard Top 100 more than 10 times, theorizing that if they are to be well-known artists then they would probably have been on it multiple times. So I wrote a dictionary comprehension (like a for loop but in one line of code) to loop the dictionary I just made and set a value that had to be equal or greater than 10 in order to make the cut.

Once I had that dictionary in place, I ran another dictionary comprehension to sort the dictionary from the greatest number to the least number, that way when I plot it, it will be easier to see who had how many songs on the charts. From there, I plotted it as a bar chart since it was just a single value, and did some small formatting so it was easier to read the artists names.


## Part 2: The Most Common Lyrics as shown via WordCloud

At this point, I was ready to start looking at the actual lyrics from the songs themselves. I first checked to see what the most common words were among ALL the lyrics from 1965 to 2015 and make it into a WordCloud. In order to do this, I had to first create a for loop to take each of the lyrics from their songs and split up the lyrics into tokens, basically each word by themselves, and then append it to one major string where all the lyrics would be held. I also converted the words into all lowercase, just to be sure that they weren't counted individually when creating the WordCloud. I then set up my WordCloud with the appropriate parameters, setting the height and width, the background color, the scaling, ensuring that collections were turned off so each word was counted individually, and setting the Stop Words, words that are not necessary to word analysis e.g "the", "a", "an", etc. From there, I set up the plotting parameters, and then let the cell run and do its thing. It took about 15 minutes maybe to run through all 5100 songs, do the operations, and then make the WordCloud, and I must say that the results were not all that surprising.

The way that WordClouds work is that the bigger the word is, the more frequent it appeared inside the lyrics. With this being said, the number one word was "love", and to be honest, I can't say that I'm surprised. Love is universal, and a very popular topic to write/sing about, and this helps to prove that. After love, the word "Im" takes second, which if I had to guess, the word that would have been next to this word is "in", but that's a stop word so it doesn't count it. After that are words like "don't", "baby", "know", "oh", "want" and "you're". I'm pretty sure that if we tried, we could write a hit song about love from the words that are in this WordCloud.

I wanted to see just how much of a trend this really was, and so I checked to see how this faired with the Top Artists dictionary that I had made earlier. I wrote a loop that took each artists name and added their songs to a new DataFrame, and then ran the same code that I used prior on this DataFrame. Lo and behold, the results are pretty much exactly the same. I can't say I'm surprised because the Top Artists would probably have the most dominant say on what is popular in terms of music.

To really push it and see just how much of a trend it was, I went and split the main dataset and split them up into decades. I went ahead and I also checked who was the top artist during that decade, and when I ran the WordCloud, added some code that would make the WordCloud in the shape of an image from that artist for each decade (bonus points if you can guess which artist is which! It'll be hard because they really aren't clear at all, but I'll tell you which is which as I go through the data).

### The 1960s
---
To start, we start with the 1960s. The top artist during this decade was __The Beatles__ with 14 songs in the Top 100 in the five year span. It will be a little harder to see the differences in top words due to them being more scattered, but no need to worry, the results here are similar to the previous data. The top word is "love", followed by "baby", "don't", "know", and "now". It seems like either nobody knows about love, or who their baby is, and whether they're in love right now. I guess we'll have to hear the songs to find out.


### The 1970s
---
Moving into the 1970s, we had a tie between __Elton John__ and the __Bee Gees__ with 12 songs in the Top 100 each, but I went with Elton John because I saw his name first. As we look at his WordCloud, we see the same trend with "love" taking the first spot, followed by a close tie with "baby", "don't", "know", "got", "you're", "come", and "time".


### The 1980s
---
In the 1980s, we have __Madonna__ as our top artist with 18 songs in the Billboard Top 100 over the course of the decade. The top words were yet again "love", followed by "don't", "know", "oh", "baby", "time", and "Im".


### The 1990s
---
Grooving on into the 1990s, we have __Mariah Carey__ as the Top Artist of the decade with 19 songs on the Top 100 over the decade. We have the word "love", followed by "don't", "know", "baby", "oh", "yeah" (songs were getting a little more sensual I guess), "ill", "I'm", "want", and "you're".


### The 2000s
---
Boy-banding our way into the 2000s, __P!nk__ and __Kelly Clarkson__ were the Top artists with 13 songs each in the Top 100 over the course of the decade (I'll let you decide which artist I used for this one). This time "love" and "Im" actually seem to be relatively close in terms of most common words, followed by the usual suspects "don't", "know", "got", and "girl" moving up in the ranks of most common words. 

### The 2010s
---
For the 2010s, this data ends at 2015. I might add up to 2019 in the future (if I could find the data), but for right now, __Taylor Swift__ was the Top Artist in the first half with 15 songs in the Top 100. In a surprise twist that's not too visible in this WordCloud, "Im" was actually the number one most common word, followed by "love", "don't", "know", "baby", "oh", "yeah", "girl", "let", "make", "you're", and "now".


## The Conclusion

Overall, the data seemed to prove kind of what had already been known by probably most of the world already, that love is the thing that brings everybody together, and we just can't stop singing about it. *Really, let's be original people.* <-- __Sarcasm__

I hope that you enjoyed going through this extensive research (that was a lot of the same stuff), and in my next attempt, I'll try to find the data for the last half the decade, and maybe, just maybe, I try and write some code that will let me generate some lyrics based on these most common words.
