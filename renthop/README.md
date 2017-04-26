## Kaggle Two Sigma Renthop competition (ended Apr 25, 2017, got #47)

It's a bit rough, since I was writing code in a hurry near the end of the competition (I remembered that I could do out-of-bag validation for my stacking) - and definitely a level down from the top participants, but there's some good stuff in it. 

### Things I did:

- I wrote a stacking class (~100-150 LOC) and formatted my models to output data compatible with it.  It was nice and orthagonal until last night* - in that I could concat the train+test output and use it for L2, and the test output (with listing_id as index) could be submitted directly from the dataframe's CSV output.

Originally I used a Keras NN, but wound up going with lightgbm for testing and xgb for submitting (I got the NN idea from my CNN Description processing, which I didn't actually use in my final submissions, and lopped off the bottom bit of it to make a stacker... which gave me another key idea:

(* - I decided to keep each fold's test predictions seperated, and I kludged the models output to be the original dataframe along with an np.array.  Crude but it actually worked.)

- I made both classification and regression models, relying on the stacker to convert 0 to 1 into the three categories.  This allowed me to make two somewhat different models with xgboost and lightgbm.

### Things I used:

- Bits and pieces of various starter scripts, including the lightgbm starter.  Since I do my non-GPU Kaggling using the official Docker container, I didn't have any setup issues.

- Kaz's L1 StackNet models, with my own stacking code.

- The leak.  I have the picture .zip file and could have pretty quickly reproduced Kaz's data, but I just used his .zip.

- Adams' features posted yesterday.

### What I could have done differently

- Gotten used to stacking a lot sooner (true for Kaggle as a whole really)

- Realizing I could (and should!) do an out of fold CV to verify quality of my stacking before the 11th hour ;)   I implemented it Monday night so I wasn't able to utilize it to tune my models as much as I should have, but ah well.

