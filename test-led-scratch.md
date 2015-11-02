# Test a connected LED with Scratch

1.  Launch the program **Scratch** by clicking on **Menu** followed by **Programming** and selecting **Scratch**. 

 ![](images/scratch-icon.png)

 *Note: Our version of Scratch on Raspbian is extra special. It allows you to access and control the GPIO pins.* 

1. Click on **Edit** and **Start GPIO server** if it has not been started already.

    ![](images/Scratch-interface.png "The Scratch Interface")

1.  Click on **control** in the top left display. Drag the `when Sprite1 clicked` block onto the scripts area. 

1. Drag a `broadcast` block to your scripts area and attach it to the `when Sprite1 clicked` block. Click on the drop down menu on the broadcast block and select **new**.

    In the message name box type `config18output` This instruction will tell the Raspberry Pi to set GPIO pin 18 as an output.

    ![](images/pin11on.png)

1. Drag another `broadcast` block to your scripts area and attach it to the bottom of first broadcast block. Click on the drop down menu on the broadcast block and select **new**.

    In the message name box type `gpio18on` This instruction will tell the Raspberry Pi to set GPIO pin 18 `HIGH`.

1. Drag a `wait 1 secs` block onto the scripts area and connect it to the previous broadcast block.

1. Drag one last `broadcast` block onto your scripts area and connect it to the `wait 1 secs` block. Click on the drop down menu on the broadcast block and select **new**.

    In the message name box type `gpio18off` This will switch off the LED.

1. Save your work so far by clicking on **File** and **Save As**. Name your file `Test LED` and click **OK**.

1. Test your program by clicking on the large cat sprite. You should see the LED come on for 1 second and then turn off.

    ![](images/pin11off.png "Turn pin 11 off")

[Back to getting started with physical computing](worksheet.md)
