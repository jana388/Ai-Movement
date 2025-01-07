# Ai-Movement
## In this tutorial I will explain how to make an Ai object to follow your player

So you would like to have an NPC in your 3D game that will follow you while you move?
This is a tutorial for you!

It is very simple and requires just a few lines of code!

This is the what the final output looks like:

https://github.com/user-attachments/assets/23248a49-693c-495e-9c9b-55252cc1a950

Although it is beginner friendly, I would like to add some prerequesites before making any further steps. 
You shold have Unity (2022.3.46f1 preferably) and Microsoft Visual studio 2022 installed, but any recent version of Unity should work too.

It is also recommended to know how to navigate through Unity and know the basics like adding a 3D object and components to the objects.
If you are a complete beginner or need a refresher chack this tutorial out first:

https://youtu.be/E6A4WvsDeLE?si=lHhy56q0yDNIGyZZ

> This tutorial is using a bit older version of Unity, but 99% of the assets we use is the same
> There are pinned updates in the description, but for the basics, using this version should not be too confusing

Another thing to note, this code is only applicable if one has a script for a player movement
In this tutorial you will only need a script for left and right movement. 

If you need any assistance with the player movement script, here is the link you can check out:

https://youtu.be/b3xgCUlst88?si=sf3RKrKG0RYrsJjW&t=697

# Setting the Player

I already made a **Cube**  and named it *'Player'*, added a **Rigidbody** to it as well as the *`PlayerMovement`* script to it.

I also added a plane as a surface because we want to use physics when moving our player.

> Adding a Rigidbody to an object adds gravity to it, so adding a plane will stop the object from endless falling.

Now that we have a Player and a *PlayerMovement script*, we can start working on our **Ai player**!

# Setting the Ai

I added a cube for our **Ai player** and named it *Ai* so we can differentiate it from the *Player*.

![1](https://github.com/user-attachments/assets/5b322dd6-78ce-428f-8cfb-c0da5cf5812e)

I have added a **rigidbody component** so it can have physics and move later in the game. Adding this, I would also like to edit some options for rigidbody so the cube does not rotate when moving. I simply it to slide on the surface of the platform.

![Screenshot 2024-12-23 042634](https://github.com/user-attachments/assets/5986018f-f55f-43e6-885b-a60a040def47)

> I have disabled the rotation on x y and z axis, so the box does not roll over

After this, we will add a C# script and name it `AiMovement`

![Screenshot 2024-12-23 002647](https://github.com/user-attachments/assets/7c1fd53a-6e04-4a73-92b6-732939f17a7f)


## Coding the AI

Now we can open the script in the *Microsoft Visual Studio*

The first thing we will do is erase first two lines of code because we will not need to use these two engines to run this code.

![Screenshot 2024-12-23 003531](https://github.com/user-attachments/assets/95bd70e9-d415-4d1b-bc53-c147593c8250)


Because our Ai is not controlled by an input, we need to inform the computer what will give Ai the directions. It will be just a few lines of code which compare the transformation of the Player and the Ai on the Z axis and change the position of the Ai.

Firstly we will go put a `public float` for speed which will determine the speed of the Ai player. 
We will put this above the `Start void` because we want it to work before any other action.

![Screenshot 2024-12-23 041513](https://github.com/user-attachments/assets/c4ccf4dd-100c-4f38-a914-73b560209b53)

Since it is a `public float` *(it is adjustable inside Unity)*, we can go to the inspector to set the speed

![Screenshot 2024-12-23 041757](https://github.com/user-attachments/assets/fde2b894-d134-4872-9a36-dc6713fe534b)

As you can see, I have adjusted it to 3 as I would like my Ai to be a bit slower than my player.


Underneath that, I will add a `private Rigidbody`.

![Screenshot 2024-12-23 042111](https://github.com/user-attachments/assets/765ab61d-25d3-4375-83bd-b9cbe3698daf)

> This will enable physics for the player

Now we will go to the `Start void` and type in the `rb component` for the rigidbody

![Screenshot 2024-12-23 042129](https://github.com/user-attachments/assets/110b0382-d5d6-4d96-a93d-eb9f2578da7f)

After that, I would like to **save the script** and head back to Unity.

Since we want our player to lead the Ai, we will use a **tag method** in the code. To connect the *AiMovement* with the *PlayerMovement*, I will add a tag to the **Player** and name it *Player*.

![Screenshot (365)q](https://github.com/user-attachments/assets/49e977f3-629f-4924-a80b-4b0f7b38ed61)


Having done this, we can return to Visual studio and add this line
> We are using Tag so we can recall the Players script and connect Ai object with the Player.
>
> Remember to use the exact same name of the object, because if not naming it correctly, the Tag would not be possible!

![Screenshot 2024-12-23 042147](https://github.com/user-attachments/assets/b27de3f5-b978-4e70-ae8c-055bdbaa5495)

Later we will go to the `Update void`, because we want this action to be constantly updated by the computer

![Screenshot 2024-12-23 042823](https://github.com/user-attachments/assets/132a2824-6d0c-4c5d-8b36-6e87e7e18c6a)

> In this code line of script, we are comparing the position of the Player with the position of the Ai
> 
> We are using the z axis since we want the players to move left and right
> 
> This means that if the *Player* is moving to the right (in code `forward` for z axis), the *Ai* will move to the right
> 
> We are using `else if` because if the first condition is not right we want the second one to count
> 
> So if the *Player* is moving to the left (in code `back` for z axis), the *Ai* will also move to the left
> 
> If none of these conditions are true (hence the `else`) or the *Player* is not moving at all, the *Ai* will not move either

If you managed to get this code right, you are good to go!

# Checking the script

Save the script and go back to Unity. 


If you press play and move your player by clicking *A* and *D* and the Ai follows, congrats!

You have learned how to make an Ai move!









