# Test plan


# HIGH LEVEL TEST PLAN 

| Test ID | Description | Input | Expected output | Actual Output | 
| --- | --- | --- | --- | --- | 
| 01 | Print Window Status | USER BUTTON PRESS ONCE  | Shall Print Window Status of the car | Shall Print Window Status the of car  | 
| 02 | Print Alarm Status | USER BUTTON PRESS TWICE | Shall Print Alarm Status of the car |  Shall Print Alarm Status of the car | 
| 03 | Print Car Battery Info | USER BUTTON PRESS THREE TIMES | Shall Print Car Battery Info | Shall Print Car Battery Info |
| 04 | Print Door status | Shall Print Door status of the car |  | Shall Print Door status of the car  |



## LOW LEVEL TEST PLAN

| Test ID | Description | Input | Expected output | Actual Output | passed/not |
| --- | --- | --- | --- | --- | --- |
| 01 | Check for Print Window Status | USER BUTTON PRESS ONCE  | Shall ON all LED's  | Shall ON all LED's  | passed |
| 02 | Check for Print Alarm Status | USER BUTTON PRESS TWICE  | Shall OFF all LED's  | Shall OFF all LED's  | passed|
| 03 | Check for Print Car Battery Info | USER BUTTON PRESS THREE TIMES | Shall ON LED's ONCE clockwise  |  Shall ON LED's ONCE clockwise  | passed|
| 04 | Check for Print Door status | USER BUTTON PRESS FOUR TIMES | Shall ON LED's once anti-clockwise  |  Shall ON LED's once anti-clockwise  | passed|
| 05 | Check for btn_press() | counts no of button press  | 1/2/3/4 | 1/2/3/4 | passed |


