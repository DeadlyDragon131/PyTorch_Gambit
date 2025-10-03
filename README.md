# PyTorch_Gambit
An AI that learns strategy by observing millions of moves, not by memorizing rules

## Intro and Motivation
Being an ardent chess fan, I was always impressed by the depth and accuracy to which chess engines calculate moves.  
I got curious about the bots like Magnus Carlsen, Hikaru Nakamura on chess.com and wanted to analyze how it would be to just 
train the data of top players with an ML model and observe its performance. This motivated me to try this out. 

## About
Hey, This is Muthu S.  
In this project we are going to use Convolutional Neural Networks (CNN) in PyTorch to build a simple chess engine.  
This works more based on our supervised training on huge Lichess datasets ; rather than through concrete rule based understanding of the game.  
So this is actually a unique approach unlike the regular unsupervised RL type models.

## Working
**Database Used:** Lichess Open Database  

The working of PyTorch_Gambit can be summarized in three main steps:

1. **Data Processing**  
   - Extract millions of games from the Lichess Open Database.  
   - Convert each game into board states and corresponding expert moves (from top player games).  
   - Represent the chessboard as input tensors suitable for CNN processing.  

2. **Model Training**  
   - Use a Convolutional Neural Network (CNN) to learn spatial patterns on the board.  
   - Supervised training is performed where the model predicts the next move given a board state.  
   - The goal is to mimic human-like play patterns by learning from actual grandmaster-level data.  

3. **Prediction / Playing**  
   - Once trained, the engine can take a board position as input and output move probabilities.  
   - The move with the highest probability (or a top-N choice) is selected.  
   - Unlike traditional rule-based engines, PyTorch_Gambit plays by imitating strategies it has learned.  

## Performance and Conclusion

### Performance
The model currently plays at an estimated **~1500 Elo** level in the opening and middlegame, but its strength drops in deeper tactical positions due to lack of search.  

### Conclusion
PyTorch_Gambit shows that a supervised CNN can learn human-like chess strategies directly from grandmaster games, without explicit rules.  

### Possible Improvements
- Add a lightweight **search** (1–2 ply) to avoid tactical blunders.  
- Train on **larger datasets** for better coverage of rare positions.  
- Fine-tune with **reinforcement learning or self-play** to strengthen beyond imitation.  
