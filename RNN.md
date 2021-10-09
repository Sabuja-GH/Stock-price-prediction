RNN has short term memory, use for time series analysis

Three Types of RNNs 

the neurons in RNN are connected to themselves over time.

 one to many example the given image and an output we get the description of the image

many to one input we give and review and an output we get the sentiment of the review

many to many translating sentences from one language to another



recurring wait w rate it is the weight that connect the same neurone overtime why back propagating after calculating the air the w rake is multiplied again and again to the initial weight which was small. so continuous multiplication  make the gradient lens in the initial time and the lower gradient make the network difficult to update the weight and longer to find final result so the initial layers of the network is not properly trained and those are used as input device for the layers



To sum up, if wrec is small, you have vanishing gradient problem, and if wrec is large, you have exploding gradient problem.

vanishing gradient problem solved by LTSM.