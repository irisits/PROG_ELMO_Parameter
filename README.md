# Motor Driver Parameters Documentation

This document provides a detailed explanation of the parameters used for configuring the motor driver.

## Parameters

**Commutation Array**
1. **CA[1]**: Digital Hall sensor A polarity
   - 1 = HIGH (default)
   - 0 = LOW

2. **CA[2]**: Digital Hall sensor B polarity
   - 1 = HIGH (default)
   - 0 = LOW

3. **CA[3]**: Digital Hall sensor C polarity
   - 1 = HIGH (default)
   - 0 = LOW

4. **CA[4]**: Actual Hall sensor connector to Hall A connector pin
   - 1 = A
   - 2 = B
   - 3 = C (default)

5. **CA[5]**: Actual Hall sensor connector to Hall B connector pin
   - 1 = A
   - 2 = B (default)
   - 3 = C

6. **CA[6]**: Actual Hall sensor connector to Hall C connector pin
   - 1 = A (default)
   - 2 = B
   - 3 = C

7. **CA[16]**: Feedback direction
   - 0 = Use feedback reading as is
   - 1 = Invert the direction of the feedback reading (default)

8. **CA[17]**: Commutation sensor
   - 0…4 = Reserved for compatibility
   - 8 = Digital Hall sensor commutation aided by external feedback

9. **CA[18]**: Feedback bits ("counts") per revolution, after resolution is multiplied by 4, in the range [6…530,000,000]
   - 4000 (default)

10. **CA[19]**: Number of motor pole pairs
    - 1…50
    - 4 (default)

11. **CA[20]**: Digital Hall sensors present
    - 0 = No digital Hall sensors connected
    - 1 = Digital Hall sensors connected (default)

12. **CA[21]**: Position sensor present
    - 0 = Ignore position sensor inputs
    - 1 = Position sensor will be used for commutation

13. **CA[22]**: Main feedback type
    - 0 = Reserved
    - 1 = Input from Resolver
    - 2 = Input for quadrature incremental encoder signals (default)
    - 3 = Input for analog sine/cosine signal
    - 4 = Input for Tachometer signal
    - 5 = Input for Tachometer signal
    - 6 = Input for digital Hall signals
    - 7 = Reserved
    - 8 = Input for Potentiometer feedback
    - 9 = Input for Analog Halls feedback
    - 10 = Input for Absolute Coarse/Fine Encoder type
    - 11 = Input for analog sine/cosine signal and absolute position value over several serial protocol formats

14. **CA[25]**: Motor direction
    - 0 = Reverse phase driving so that the motor direction with positive torque command is reversed
    - 1 = Keep the original motor direction, as connected by user (default)

**LIMIT**
1. **MC**: Maximum peak driver current (Read-only parameter)

2. **PL[1]**: Motor maximum peak current
   - Range: 0…MC
   - 30.0f (default)

3. **PL[2]**: Motor maximum peak duration
   - Range: 1…3

4. **CL[1]**: Maximum allowed continuous motor phase current
   - Range: 0…MC/2
   - 10.0f (default)

5. **HL[2]**: High speed limit
   - Range: Velocity range
   - 3000 (default)

6. **LL[2]**: Low speed limit
   - Range: Velocity range
   - -3000 (default)

7. **HL[3]**: High position limit
   - Range: -2^31 < HL[3] < 2^31 – 1
   - 999999990 (default)

8. **LL[3]**: Low position limit
    - Range: -2^31 < LL[3] < 2^31 – 1
    - -999999990 (default)

9. **GS[14]**: Maximum speed error for which KP[N] is cleared in speed controller if no encounter count exceeds GS[0]
    - Range: 0...0…2^31 - 1
    - 6300 (default)

**PI Parameter**
1. **KP[1]**: PI current control filter
   - 0.593f (default)

2. **KI[1]**: PI current control filter
   - 828.0f (default)

3. **KP[2]**: PI velocity control filter
   - 60.0f (default)

4. **KI[2]**: PI velocity control filter
   - 2000.0f (default)

**Mode of Operation**
1. **PM**: Profiler Mode
   - 0 = For UM=2, AC, DC, and SF are not used (default)
   - 1 = For UM=2, AC, DC, and SF are used normally

2. **SF**: Smooth Factor
   - Defines the motion smoothing factor for PTP and jogging motions
   - 0 (default)

3. **AC**: Acceleration
   - Defines the maximum acceleration in counts/second²
   - 8307415 (default)

4. **DC**: Deceleration
   - Defines the maximum deceleration in counts/second²
   - 8307415 (default)
