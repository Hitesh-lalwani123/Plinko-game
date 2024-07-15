## Plinko Game

                *    0    *   +1  *
            
            *         *       *        *
    
        *         *       *       *         *

    *        *        *       *        *         *                 
    -----------------------------------------------
    |   5x   |   1.2x |  0.5x |   1.2x |   5x    |
    -----------------------------------------------
 
If a user bets: 
1. say server calculates probabilities and finds that the user should land at 1.2x
2. Server chooses randomly from 0 and +1 for the ball to drop on the first drop.Say 0.

3. Server has a list of precalculated distances of all the outcomes.
4. From 0's pov
 
                *    0    *   +1  *
            
            *        *        *        *
    
        *       *         *       *         *

    *       *        *        *        *         *  
        -3       -1       +1      +3        +4           
    -----------------------------------------------
    |   5x   |   1.2x |  0.5x |   1.2x |   5x    |
    -----------------------------------------------
    So to achieve the outcomes in 3 rows the results will be:
    - 0.5x: +1,           --> +2-1(RRL)
    - 1.2x: -1,+3,        --> -2+1(LLR), +3(RRR)
    - 5x  : -3,+4         --> -3(LLL), +4 is not possible

    Now any of the above strings can be rearranged randomly and returned to the client
5. 
                *    0    *   +1  *
            
            *        *        *        *
    
        *       *         *       *         *

    *       *        *        *        *         *  
        -4       -3       -1      +1        +3           
    -----------------------------------------------
    |   5x   |   1.2x |  0.5x |   1.2x |   5x    |
    -----------------------------------------------
    So to achieve the outcomes in 3 rows the results will be:
    - 0.5x: -1,           --> -2+1(LLR)
    - 1.2x: -3,+1,        --> -3(LLL), +2-1(RRL)
    - 5x  : -4,+3         --> +3(RRR)

    Now any of the above strings can be rearranged randomly and returned to the client