# HearthStone-Battleground-Top4-Predict
A model to predict whether you will be top 4 according to datas before 10 coins

The HearthBattlePredict.m file is the main file for training the prediction model. The model was mainly an one vs all model trying to predict whether you can reach top 4 in a game. The program was implemented with Matlab.

# History
Someone may ask that can your model predict the rank of a game? Probably. But the diagnose.m indicates that the model is a high bias one. You can see the figure in LearningCurveForRankPredicting.fig.
As we know, to solve high bias, we may increase the features. 
However: 1. for manual record, it's hard to get all the details; 2. we only have information before 10 coins. Due to the two reasons, the model is hard to modify. Maybe I will figure out some other solution to it.

# Data
I designed 8 features as input data. Including:
1. Hero's tier;
2. Have a derivative (e.g. 1/1 tiger) when coin 3 or not;
3. Number of derivatives (e.g. 1/1 tiger) until coin 6;
4. Hero's health at coin 10;
5. Inn tier at coin 10; 
6. Average tier of your opponents until coin 10;
7. Victories until coin 10; 
8. Number of golden cards until coin 10.

# Log
2020.01.10

I have collected more than 100 games datas and the accuracy of the model is around 80%. However, the accuracy of rank prediction is only 50%.

2020.01.17

I modified the features of the datas. There are 14 features now.
1. Hero's tier;
2. Have a derivative (e.g. 1/1 tiger) when coin 3 or not;
3. Number of derivatives (e.g. 1/1 tiger) until coin 6;

4. Hero's health at coin 10;
5. Average tier of yourself until coin 10;
6. Average tier of your opponents until coin 10;
7. Average minions you bought until coin 10;
8. Number of your hero ability used until coin 10;
9. Number of frozen until coin 10;
10. Number of wasted coins until coin 10;
11. Number of wins until coin 10;
12. Number of ties until coin 10;
13. Number of loses until coin 10;
14. Number of golden cards until coin 10.

2020.01.22

I collected 20 new datas as a small cross validation (cv) set. However, the accuracy of the model was just 55%. The rank prediction accuracy wass just 5%. I had about 120 datas in all. I splited the datas into two halves as training set and cv set. The accuracy of the model was nearly 65% and the rank prediction accuracy was nearly 27%. Seems that the elder model with 8 features was a typical high variance model and I ran into overfitting problem. Maybe I should try the new 14 features model.
