# Survive Game

### Overview
SurviveGame is a mobile application created for a mobile security course. The aim is to navigate through various levels, finding ways to survive and reach your city. Players input a specific ID at the start, which affects gameplay and the steps needed to complete each level.

### Identifying and Bugs Fixing
#### `Activity_Game.java`
1. **Update Toast Messages:**
    From:
    ```java
    Toast.makeText(this, "Survived in " + state, 1).show();
    } else {
    Toast.makeText(this, "You Failed ", 1).show();
    ```
    Modify to:
    ```java
    Toast.makeText(this, "Survived in " + state, Toast.LENGTH_SHORT).show();
    } else {
    Toast.makeText(this, "You Failed ", Toast.LENGTH_SHORT).show();
    ```

2. **Update Integer Parsing:**
   From:
    ```java
    iArr[i] = Integer.valueOf(String.valueOf(id.charAt(i))).intValue() % 4;
    ```
    Modify to:
    ```java
    iArr[i] = Integer.parseInt(String.valueOf(id.charAt(i))) % 4;
    ```

3. **Fix the URL.**


### Implementation of Required Adjustments
- Improved the display duration of toast messages.
- Simplified the integer parsing process.

### Testing and Verification
- Tested the application on emulator.
- Verified that game mechanics function properly and the correct toast messages are displayed in scenarios of success/failure.

### Example ID and Steps
1. **Enter a valid ID:**
    - Example ID: "207354614"
    - Steps:
       - The `steps` array will be as follows:
          - index 0 ('2') -> 2 % 4 = 2 (Up)
          - index 1 ('0') -> 0 % 4 = 0 (Left)
          - index 2 ('7') -> 7 % 4 = 3 (Down)
          - index 3 ('3') -> 3 % 4 = 3 (Down)
          - index 4 ('5') -> 5 % 4 = 1 (Right)
          - index 5 ('4') -> 4 % 4 = 0 (Left)
          - index 6 ('6') -> 6 % 4 = 2 (Up)
          - index 7 ('1') -> 1 % 4 = 1 (Right)
          - index 8 ('4') -> 4 % 4 = 0 (Left)

2. **Follow the steps:**
    - Press the buttons in the order derived from the ID.
    - Try other buttons to verify failure for the same ID.
