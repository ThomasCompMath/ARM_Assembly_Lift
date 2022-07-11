# ARM_Assembly_Lift
Some code for controlling an elevator with a Rasberry Pi

The following code is written with the idea of controlling an elevator with a Rasberry Pi.
The primary purpose was to practice ARM Assembly, so hardware considerations and safety considerations were hardly considered.
There are still plently of bugs in the code or portions of the code, where I closed an opening with a shortcut that would function in a less than ideal way on an actual Rasberry Pi controlled elevator.

See the attached image for a visual representation of the lift in mind.
  On the image:
  The labels at the top represent hardware on the emulator or RAM addresses to monitor as the code runs.
  The red objects are buttons.
  The pink objects are sensors, although I forgot to have the code make use of several of them.
  The objects labelled in blue are the outputs, the motors.

As for the algorithm:
  The code runs in a continuous loop.
  To start the program, the lift must be on the ground floor, as the code zeros the encoder.
  The doors must be closed, as the code initializes them to this position.
  The code also clears all the registers, in case there was something hanging over from the previous iteration.
  The switches are red.
  If no switch (button) is active, then the code loops back to the top.
  If any button is pressed, then the code will jump to the code for that floor, check to see whether up or down is required, and execute movement.
  If multiple buttons are pressed, you'll just break the code.
  The code checks if the doors are closed before moving, but if they are not closed, it just exits, obviously not ideal.
  When it moves, the encoder value just loops through a few numbers until it hits the value that represents the desired floor.
  Once the desired floor is reached, the doors open (instantaneously), a counter loops to allow people to exit, the doors close (instantaneously), and the program goes     back to the start.
  
 Enjoy!
 
 Special thanks to whoever made the wonderful emulator I used at: https://cpulator.01xz.net/?sys=arm-de1soc
