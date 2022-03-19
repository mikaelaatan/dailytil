I've been using Google Colab for my cryptography homeworks, since I found that the runtime lasts longer when I need to use an external API to validate the decryption. 

This Python code is from [Stackoverflow](https://stackoverflow.com/questions/57113226/how-to-prevent-google-colab-from-disconnecting) that basically acts as a mouse jiggler to make Colab believe that user is still active. This allowed me to run the code overnight. 

```python
import numpy as np
import time
import mouse
import threading

def move_mouse():
    while True:
        random_row = np.random.random_sample()*100
        random_col = np.random.random_sample()*10
        random_time = np.random.random_sample()*np.random.random_sample() * 100
        mouse.wheel(1000)
        mouse.wheel(-1000)
        mouse.move(random_row, random_col, absolute=False, duration=0.2)
        mouse.move(-random_row, -random_col, absolute=False, duration = 0.2)
        mouse.LEFT
        time.sleep(random_time)


x = threading.Thread(target=move_mouse)
x.start()
```

Instructions: 
1. Save the code as mouse_mover.py.
2. Using shell/terminal, run `python mouse_mover.py`
3. Run your code in Google colab and make sure that the browser is in focus.

This has been a life-saver as I had to decrypt messages that took more than 5 hours for my cryptography class. 