# Bed Level Estimate

Bed leveling happens later in the process, but I have found that it is worth getting an estimate on how level it is early on.

If you get the bed approximately correct now, fine tuning will be better later.


</br></br>
---
## Process

1. Preheat the bed to normal temp
2. Home the print head
3. In mainsail, go to the 'heightmap' tab, and click calibrate

Alternatively you can use the `BED_MESH_CALIBRATE` command.


</br></br>
In mainsail, we will get a nice visual to show us how level the bed is.

In some cases like this one, the bed level is way out. The range is very large (0.542mm in this case).

<img width="330" height="266" alt="image" src="https://github.com/user-attachments/assets/5d58fdce-ef70-4b7f-ad3d-cfac467a8384" />

<img width="274" height="147" alt="image" src="https://github.com/user-attachments/assets/6e3e1b32-6223-411a-adfa-4329db8458bd" />


</br></br>
We can leave it as it is and let software handle it. However, this is not always ideal, as the software was really only meant for fine tuning.

This needs manual leveling, which usually means adding spacers under the print bed, or changing them.


</br></br>
In this case, the front left side is too high. I did this:

1. Raised the print head up, so it wont be in the way
2. Cooled the printer down, and turned it off
3. Removed the print bed
4. Took out the front left spacer, and sanded it down (only very slightly)


</br></br>
I ended up getting the corners to be similar heights.

<img width="339" height="271" alt="image" src="https://github.com/user-attachments/assets/e7e6e906-a600-43a0-ae51-995fa25dceb1" />


