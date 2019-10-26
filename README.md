Tips of higher accuracy
===
- one case, only lower case

To train the model
===
- 1. Prepare the testing data fix fastText format e.g. [Twitter Data in Kaggle](https://github.com/wingleungchoi/twitterKaggle)
  - i. wc ./trainData/output.txt
  - ii. head -n 90000 ./trainData/output.txt > ./trainData/tweets.train
  - iii. tail -n 10000 ./trainData/output.txt > ./trainData/tweets.valid
- 2. Train (supervised) the model with data
  - i. ./fasttext supervised -input ./trainData/tweets.train -output model_tweets -lr 0.5 -epoch 25 -wordNgrams 2 -loss hs
- 3. Test the accuracy of the model
  - i. ./fasttext test model_tweets.bin ./trainData/tweets.valid
