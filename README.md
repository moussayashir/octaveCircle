# octaveCircle
New type of musical keyboard interface

The UX is responsive. 

![image](https://github.com/user-attachments/assets/5a09da9d-6f12-4ddc-b85b-2db3af3161b5)



1. **Clockface background:**     
1.1 The background is a circle, with 12 very thin (1 px) radial lines, creating 12 "slices".     
1.2 The radial lines are between the hours rather than on the hours.    
1.3 The slices (between the radial lines) are alternately colored with light gray and white.     
Just to be clear:  The slice means the complete empty area between each two radial lines. It is with only one color. Gray or white.     
So for example:     
The 12 ocklock slice is a slice between two lines: the left side line of this slice is on the 11:30 hour line, and the right side line is on the 12:30 hour line. All that area between these two lines is the slice. It has one color only: Gray.     
The 1 o'clock slice is a slice between 12:30 and 1:30.  All that area in the slice is white.     

2. **Controls**     
2.1 The control section: In the center of the circle, there is a white control circle, just enough in size to contain a triangle of 3 small buttons:     
2.2 **Contol buttons**    
2.2.1 The Stop button. A small circular Red button with a square stop-playing icon in it. Pressing it stops all sounds.    
2.2.2 Two Radio Buttons with the choice of Perc or Sust.  The sustained is green, the percussive blue.    
2.2.3 Choosing the **Perc** option will cause each note-button press to play a short piano sound. Each note ends on its own a bit after the button was pressed, regardless of whether you released the button or are still holding it down. This should be similar to pressing a real piano key.
2.24. Choosing the **Sust** option will cause the next note-button presses to continue playing a sound (perhaps oboe, or strings), until the button is released, upon which the sound will stop.     

3. **Note buttons:**     
3.1. There are 2 octaves, starting with INITIAL_OCTIVE, initially set to 2. (So we have octave 2 and octave 3).     
3.2 There are 24 small circular note buttons, 12 in each octave.     
3.3 Each octave starts with A, and ends with G#.     
3.4 The note buttons have the following properties: octave, hour, note, solfege, isNatural (meaning is it a white key).     

3.5a. **Starting note:** The first note (A) is at the 01:00 angle, close to the control circle.     
    
3.5 **Octave spiral:** Each of the octave's buttons is positioned on the hour, with each consecutive button moved a slight nudge outwards.     
So A is at 1:00, A# at 2:00, B at 3:00, C at 4:00, C# at 5:00, etc. In this way the buttons begin a spiral shape.      
    
3.7 **Octaves progression:** The next octave's notes are also on the hour, directly outside (above) the button from the octave below, (further away from the center)  So, for example, both A2 and A3 are on the 1 hour, with A2 closer to the center.     
    
3.8 **Initial octave:** The notes begin at OCTNUM which is initially 2. So the first note is A2.  

3.9. **Octave transition:** Inside each octave at the transition from B to C the octave number of that note goes up one.     
So we have: Octave 2:     
A2 A#2 B2, C3 C#3, D3, D#3, E3, F3, F#3, G3, G#3.     
And Octave 3:    
A3, A#3, B3, C4, C#4, D4, D#4, E4, F4, F#4, G4, G#4    
    
3.10. **Natural vs sharps**:      
3.10.1 **Colors:** The natural notes A B C D E F G are light blue buttons with dark blue text.  The sharps are navy blue with white text.     
3.10.2 **Text:**     
a. The natural notes have the octave number, a dot, and the hour. Below the number, they have the solfege name of the note.     
b. The sharp notes have the octave, a dot and the hour.      
    
3.11. Sounds:  When a note button is pressed, its note is played, according to the selected control: Percussion or Sustained.     
    
**Spiral**  A small dot is placed on the spot between each pair of buttons on the same octave (which is on the same hour).     
A thin 2px line is drawn between those dots, creating a spiral.     
    
**Chords**.  In the top right corner, there is a Chords mode toggle button (on or off).     
1. When chord mode is on, Each note button will have two tiny buttons attached, one on the right (for minor) and one on the left (for major).     
2. Pressing a major or a minor button does the following:     
2.1 Plays the 3 notes of that chord.     
2.2 Draws a green line between the two first note buttons. Draws a gray line between the last chord's note and the first chord's note on the other octave. If one of the chord notes is not on the keyboard, it uses the note from the other octave.     
