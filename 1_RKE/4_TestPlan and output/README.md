
# Test plan
HIGH LEVEL TEST PLAN
| ID |	Description |	Input 	|Expected output 	|Actual Output|
|--|--------------------------------------------------------|
|1| 	Lock| Press Button Once |	Shall Lock the car |	Shall Lock the car|
|2|	Unlock | Press Button  Twice 	|Shall Unlock the car 	|Shall Unlock the car|
|3|	Alarm Activate / Deactivate | Press Button Three Times 	|Shall Activate / Deactivate Alarm |	Shall Activate / Deactivate Alarm|
|4|	Approach Light|  Press Button four times |Shall turn On approach light |	Shall turn On approach light|

LOW LEVEL TEST PLAN

| ID |Description |	Input |	Expected output| 	Actual Output| 	passed/not|
|1 |	Check for Lock|Press Button Once 	| 	Shall ON all LED's as per ENCRYPTION 	Shall ON all LED's as per ENCRYPTION 	✅
|2 	|Check for Unlock |	USER BUTTON PRESS TWICE 	Shall OFF all LED's as per ENCRYPTION 	Shall OFF all LED's as per ENCRYPTION 	✅
|3 	|Check for  Alarm Activate / Deactivate | 	USER BUTTON PRESS THREE TIMES 	Shall ON LED's ONCE clockwise as per ENCRYPTION 	Shall ON LED's ONCE clockwise as per ENCRYPTION 	✅
|4 |	Check for Approach Light|	USER BUTTON PRESS FOUR TIMES 	Shall ON LED's once anti-clockwise as per ENCRYPTION 	Shall ON LED's once anti-clockwise as per ENCRYPTION 	✅
