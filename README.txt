Name: Benjamin Kim
Collaborators: None
Class: CS 480
Summary: I decided to make a spider for this assignment. All in all, it has 28 components. A body, face, 2 eyes, 2 pupils, 2 teeth, 2 parts for its tail, and 6 limbs made up by 3 links each. To create the right limbs, I used the code for the left limbs, but gave the right ones a negative-x coordinate for their positions. Additionally, for the first links for the right limbs, I rotated them by an additional 180 degrees by their u, v, and w axes, and set their default W axes to [0, 0, -1]. These additional rotations and the changing of the default w axes were done to put their rotational origins in the correct spot, and make sure additional keyboard rotations would produce the proper mirrored movements between limbs. For each limb, I made sure to take into account the rotations I had already performed to get them into their correct positions/alignments when setting their rotation limits. In Sketch.py, I changed select_obj_index to a list so the user can select multiple components simultaneously, and the functions Interrupt_Scroll and Interrupt_Keyboard. I changed Interrupt_Scroll to include a parameter for the component to be rotated, since as it was before it used select_obj_index as a static value and thus couldn't rotate multiple components simultaneously, and I made multiple changes to Interrupt_Keyboard. First, I changed selected to a list that contains all the components referenced by select_obj_index, since the code needs to know every component eligible to be changed to carry out rotations or changing their color to match the axis of rotation. Secondly, Interrupt_Keyboard now utilizes the select_or_deselect_component helper function I wrote to map keys to different components. The helper function has a parameter for the name of the component and a parameter for the list of all possible components, and it uses them to find the component itself and its index. If the index is already in select_obj_index, it deselects the component by resetting its color and removing its index from select_obj_index, but if it's not it selects the component by adding its index to select_obj_index, setting select_axis_index to 0, and setting the component's color appropriately. 

Here are the mappings from keys to components (by left/right, I mean left/right from a top-down view of the spider with it's head at the top of the screen):
1: face/head
2: right eye
3: left eye
4: right pupil
5: left pupil
6: right tooth
7: left tooth
8: body
9: upper left leg link 1 (top link)
0: upper left leg link 2
a: upper left leg link 3
s: upper right leg link 1
d: middle left leg link 1
f: middle right leg link 1
g: lower left leg link 1
h: lower right leg link 1
j: the first tail component (the cyan sphere).
