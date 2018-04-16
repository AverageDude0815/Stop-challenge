# Stop-challenge
# My first "game" in Python

from datetime import datetime

now = datetime.now()
now_str = str(now)
                
dt_obj = datetime.strptime(now_str,
                           '%Y-%m-%d %H:%M:%S.%f')
now_millisec = dt_obj.timestamp() * 1000

rando = str(now_millisec)[-3:] ##random function
sys_ready = False

try:
        for i in range(1, 1000):
                for j in range(1, 1000):
                        x=j/i
                        if x == float(rando)/i and i>=2:
                                sys_ready = True
                        if sys_ready:
                                print('now press Ctrl. & C')
                        else:
                                print(x)
                                ready = datetime.now()
                                ready_str = str(ready)                
                                dt_obj = datetime.strptime(ready_str,
                                                           '%Y-%m-%d %H:%M:%S.%f')
                                ready_millisec = dt_obj.timestamp() * 1000
except KeyboardInterrupt:
        print('')
        print('code interrupted')

if sys_ready:
        now = datetime.now()
        now_str = str(now)

        dt_obj = datetime.strptime(now_str,
                                   '%Y-%m-%d %H:%M:%S.%f')
        after_millisec = dt_obj.timestamp() * 1000
        time_delta = after_millisec - ready_millisec
        print('Your time in milliseconds = ', time_delta - 46.8) ##time needed on my computer just to run the code itself
else:
        print('Too early! You loose!')
