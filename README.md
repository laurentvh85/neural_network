# Neural Networks

In this challenge we were tasked to build our own machine learning model to predict the success of a venture for Alphabet soup.

# Data Pre-Processing:

I started by looking at the data and creating a categorical variable list of objects. The categories that looked like they needed work were NAME, APPLICATION_TYPE, and CLASSIFICATION.

I first looked at the APPLICATION_TYPE. When i ran a density plot, I could see that there was a drop off at under 1,000 values. I then decided to use binning for all values under 1k.

I repeated the same process above for the CLASSIFICATION column. I used the same cut off here as well.

I then dropped the EIN and NAME columns as I believe these are irrelevant.

I then created a OneHotEnconder instance, and fit and transformed the encoder using the categorical variable list. This transformed data was then put into a dataFrame. This was then merged with out original dataframe, and the original columns were dropped.

The next step was to split our preprocessed data into our features and target arrays. Then I split the preprocessed data into a training and testing dataset. Then I scaled the data.

# Compile, Train, Evaluate

My inputs were 40
my first layer was 80 neurons (2x the input)
second layer i used 12 neurons
I used relu activation for the layers and sigmoid for the output. The model ran for 50 epochs

The initial moved had a loss of 0.56 and an accuracy of 72.57%

- This accuracy was not enough, so I tweaked the following:
  layer 1 - 120 neurons
  This lowered the accuracy from 72.57% to 72.35%

- For the third test I reverted back to 80 neurons in the first layer. I upped the epochs to 100 and changed all activations to sigmoid. The result was slightly better at 72.66%.

- The fourth test i added another layer using sigmoid. I also upped the neurons in the second layer to 60. The third layer has 30. This dropped the accuracy to 72.5%

- The fifth test i added another layer with 15 neurons. This brought the accuracy back up to the third test at 72.65%

- The sixth test i added another layer with 7 neurons and upped the epochs to 300. this lowered the accuracy to 72.58%

- the seventh test I let run for a while as i upped the epochs to 2,000 to see if the length would make a noticeable difference. The accuracy from this was 72.56%

- I was unable to attain 75% accuracy with all the tweaking I did above.

The best result I got was an accuracy of 72.66% by using 2 layers, using sigmoid activation and 100 epochs. I tried to increase the accuracy by adding layers, upping the epochs, and upping the neurons per layer.

I would use a random forest classifier model as it is simple, and it gets very similar results. I ran one in the challenge and it showed an accuracy of 70.8% in a fraction of the time.
