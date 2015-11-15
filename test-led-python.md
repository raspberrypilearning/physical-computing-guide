# Testing a connected LED in Python

With your circuit complete, you are now ready to write some code to switch the LED on. 

1. Open Idle3 from the main menu.

    ![Open Idle3](images/open_idle.png)

1. Create a new program from the **File** -> **New Window** option

1. Enter the code below.

    ```python
    import time
    import RPi.GPIO as GPIO
    GPIO.setmode(GPIO.BCM)
    GPIO.setwarnings(False)

    led = 17

    GPIO.setup(led,GPIO.OUT)
    ```
    The first two lines tells the Python interpreter (the thing that runs the Python code) that it will be using a ‘library’. You will need the `time` library in order to add timings to your program and the `RPi.GPIO` library that will tell the Pi how to work with the Raspberry Pi’s GPIO pins. A ‘library’ gives a programming language extra commands that can be used to do something different that it previously did not know how to do. This is like adding a new channel to your TV so you can watch something different. Each pin on the Pi has several different names, so you need to tell the program which naming convention is to be used in the third line of the code. The second to last line tells Python not to print GPIO warning messages to the screen. The final line tells Python to set up pin 17 as an output.

1. Underneath the code you have just entered, type:

    ```python
    print("Light on")
    GPIO.output(led,GPIO.HIGH)
    ```
    The `print` function prints some information to the terminal. This is handy as it tells you what is happening, so that even if you LED doesn't come on you know that your program is working. If that happens then there might be something wrong with the wiring of your circuit and you should go back through the steps above to check.

    The next line turns the GPIO pin 17 ‘on’. What this actually means is that this pin is made to provide power of 3.3 volts. This is enough to turn the LED in your circuit on.

1. The code so far will turn on the LED; let's add some code to turn it off after a period of time. Below your existing code, type:

    ```python
    time.sleep(1)
    print("Light off")
    GPIO.output(led,GPIO.LOW)
    ```
    The first line adds a pause or sleep. It tells the program to sleep for one second before moving onto the next line in the sequence of code. During this time your LED will be on because you have not told it to do anything else yet. To turn the LED off, you add a line similar to the one that turned GPIO pin 17 on, instead you replace GPIO.HIGH with GPIO.LOW. This will turn the pin off so that it no longer supplies any voltage.

1. The final part to add to your program is:

    ```python
    GPIO.cleanup()
    ```

    The GPIO.cleanup() command at the end is necessary to reset the status of any GPIO pins when you exit the program. If you don’t use this, then the GPIO pins will remain at whatever state they were last set to.

1.	Save your code by clicking on **File** and **Save**.

1. It is now the moment of truth! Click on **Run** and **Run Module** to execute (or run) your code.

Back to [Getting started with physical computing](worksheet.md)
