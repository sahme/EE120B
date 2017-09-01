# EE120B
Syed Ahmed 
EE-120B 
Project: Simon (game)

Objective:
The course Introduction to Embedded Systems  at UCR provides experience with the basic elements of programming and implementing an embedded system. To test the learning and understanding of the material, the students are required to integrate the content of the class into a single project that showcases the goodprogramming standards and the use of hardware used in a basic embedded system.

High-Level (Intuitive) Functionality:
 	The game starts off by displaying a welcome message on a 9*16 LCD screen, and waits for a button to start. When a button press is detected, the game starts off by randomly lighting an LED to display the random number generated. Then the user is required to press the button corresponding with that LED. A correct answer is indicated on the LCD and the user progresses to level two. At any given level, the game adds just one random button press to the existing pattern, then displays the entire pattern, which the user is required to mimic via button presses to level up. A wrong button press restarts the game immediately, and a message is displayed. Victory is declared at 9 button presses when the game automatically restarts. The game is required to display a new random pattern each time the game is played. 

User guide:
	The main game functionality is as stated above, but the gameplay has a few added complexities. The game displays a “Let’s Begin” message when the add_pattern is executed for the first time in a game, indicating that the initial button press has been acknowledged and the game has started. After displaying the pattern, the game is immediately ready for the inputs but does not sample the inputs while the pattern is being displayed including the short waits between two LED light ups. The button must be pressed for long enough to be registered, due to the program detected multiple button presses even when only one was intended, due to the button bouncing. To accommodate this, “Reading” is constantly being refreshed on the LCD screen, when a press is detected, the message stays for a brief time before refreshing again. Also, in case a button gets stuck during a press, the game will only register one press and display a message asking the user to release the button, before the game determines if the button press was correct or not.  A correct button press results in the game waiting for the next press, if the pattern is not complete yet, leveling up if the pattern is complete but the game is not. And it displays victory when the pattern and game are both complete. The number of button presses required for victory can be adjusted in the source code by changing the value of a #define statement at the beginning of the program.  Along with the LCD screen, the messages are displayed on the LEDs as well, a level up by PB1 and PB3 lighting up, in case of a wrong answer, PB0 and PB1 light up, and when a player wins, all the LEDs light up.
Technologies:
	The game uses an Atmega 1284P microcontroller, programmed using the AVR dude, with code written and debugged on Atmel Studios 7 and RIMS. It uses four buttons, four LEDs, a 9*16 LCD screen, and buzzer to give audio feedback. 
 

 
