|SIP|Title|Status|Type|Category|Author|Created|
|--:|:--:|:--:|:--:|:--:|:--|:--:|
|4| Decrease block generation monitoring interval | Living | Process |Tool|Koji Machi (https://t.me/kojimachi)|2023-7-27|

The automatic node monitoring tool has a function to automatically restart GETH when it detects that block generation has stopped for 10 seconds.

In order to monitor the stability of the node,
it is not wrong to trigger a warning notification by stopping block generation for 10 seconds recorded by the above automatic node restart tool.
If we want to notify the operator of a warning, I think it would be better to trigger a short interval stop, such as 7 seconds.


## suggestion  
Automatic ETH restart：When 10 second block generation stop.(as before)  
Notify block generation instability：7 seconds stop.

### necessary function
Automatic restart tool : Detects 7 second stop and outputs a warning log  
Log monitoring tool : Detect 7 second stop log in real time and send email to node operators.
