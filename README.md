# cs506Midterm2



1) Data Exploration 

2) Feature Extraction / Engineering

To explore the data, I looked at correlation for all the data that we were given. I obviously stayed with finding the sentiment, polarity, and use of question marks and exclamation marks but then I further looked at some other things.

Review length: Didn't see a big correlation
VotedHelpful and TotalVotes: seemed to correlate pretty strongly. If there was a lot of votedHelpful or a lot of totalvotes scores seemed to be pretty consistently higher.
Genre: Interestingly enough, when looking at the average score of every genre the top 40 genres all had an average score of 4.9+ and the bottom 5 all had below a 2.0 rating. This gave for some correlation that was included. 
Album_id and artist_id: There also seemed to be correlation here as albums and artists would consistently be rated higher or lower depending on how liked or disliked each album and artist was. 

These were all the features that I extraced and put together for training. I messed around with weighing them differently as well as tweaking the way I used all of them (for exaxmple, I used a ratio for seeing how many votes were seen as helpful) and engineered these into my model.

3) Model Creation and Assumptions

I tried a couple different models for this. I started off with a decision tree(and random forest) as well SVM but the best seemed to be logisitc regression which makes sense because we have the discrete classifications of scores.

4) Model Tuning

I looked at a lot of different things within the logisitc regression specifically the amount of iterations as well as the C value. I worked around them all and found that letting it run without a limit on iterations gave a better performance as well as a C value of ~0.5. I even looked at adding different weights to different scores (specifically 2,3,4 because thats what the model has been struggling about)

5) Model Evaluation / Performance

For model evaluation I used the sklearn f1 score as well as total accuracy. I used both relatively equally in my evaluation when I would use 1/4 of the data set. This allowed for much better evaluation and tuning but led to problems down the line that I'll talk about later.

6) Struggles / Issues / Open Questions

I really only had one problem besides just capping out on my accuracy. This was my evaluation. Upon running it on a quarter of the set I would have a much higher f1 macro score then when I would on the entire data set which was annoying - and further more, my kaggle submission would be even lower. I assume because I was overfitting a too much but I ran out of time to do enough further testing. Would have been interesting had there been more time to try and figure out where/why overfitting was happening.
