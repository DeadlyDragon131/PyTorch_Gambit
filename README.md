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
The current model trained on the Lichess database plays at an estimated level of around **~1300 Elo** in the opening and middlegame.  
It shows good accuracy in imitating strong player moves but struggles in deeper tactical positions and longer games.  

### Conclusion
PyTorch_Gambit demonstrates that a supervised CNN trained on millions of expert moves can learn to play chess in a **human-like style** without any rule-based programming.  
While not competitive with top engines, it proves that move prediction from data alone can reach a strong club-level strength.  

### Possible Improvements
- Add a lightweight **search mechanism** (1–2 ply lookahead) to reduce tactical mistakes.  
- Train on **larger and higher-quality datasets** to improve accuracy.  
- Integrate a simple **blunder detection filter** to avoid major mistakes.  
