# Radar_2D_CFAR
### 2D CFAR
After some hyperprameter tunning I found that the best numbers is:

```matlab
Tr = 8; 
Td = 5;

Gr = 2;
Gd = 2;

offset = 6;
```
Then I made a for-loop that do:
- For every iteration sum the signal level within all the training cells. To sum convert the value from logarithmic to linear using db2pow function.
- Average the summed values for all of the training cells used. After averaging convert it back to logarithmic using pow2db.
- Further add the offset to it to determine the threshold.
- Next, compare the signal under CUT against this threshold.
- If the CUT level > threshold assign it a value of 1, else equate it to 0.
