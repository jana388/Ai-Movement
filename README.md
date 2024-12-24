# Ai-Movement
## In this tutorial I will explain how to make an Ai object to follow your player

So you would like to have an NPC in your 3D game that will follow you while you move?
This is a tutorial for you!
Although it is beginner friendly, I would like to add some prerequesites for you before making any further steps. 
You must have Unity and Microsoft Visual studio installed. I used Unity 2022.3.46f1 and Visual studio 2022, but any newer version should work too.

It is also recommended to know how to navigate through Unity and know the basics like adding a 3D object and components to the objects.

Another thing to note, this code is only applicable if one has a script for a player movement.

I already have a cube named 'Player', added a rigidbody to it as well as the `PlayerMovement` script to it.

I also added a plane as a surface because we want to use physics when moving our player.
> Adding a Rigidbody to an object adds gravity to it, so adding a plane will stop the object from endless falling.

Now that we have a Player and a Player Movement script, we can start working on our Ai object!

I added a cube for our NPC and I named it Ai so we can differentiate it from the Player.

![1](https://github.com/user-attachments/assets/5b322dd6-78ce-428f-8cfb-c0da5cf5812e)

I have added a rigidbody component so it can move later in the game. Adding this, I would also like to edit some options for rigidbody so the cube does not rotate when moving, but simply slide on the surface.
![Screenshot 2024-12-23 042634](https://github.com/user-attachments/assets/5986018f-f55f-43e6-885b-a60a040def47)
> I have disabled the roration on x y and z axis .

After this, we will add a C# script and name it `AiMovement`

![Screenshot 2024-12-23 002647](https://github.com/user-attachments/assets/7c1fd53a-6e04-4a73-92b6-732939f17a7f)

## Coding the AI

Great, now we can open the script in the Microsoft Visual Studio.

The first thing we will do is erase first two lines of code because we will not need to use these two engines to run this code.

![Screenshot 2024-12-23 003531](https://github.com/user-attachments/assets/95bd70e9-d415-4d1b-bc53-c147593c8250)


Because our Ai is not controlled by an input, we need to inform the computer what will give npc the directions. It will be just a few lines of code that compare the transformation of the player and the ai on the Z axis and relocate the ai.

Firstly we will go put a public float for speed which will determine the speed of the ai player. 
We will put this before the start void because we want it to work before any other action.
![Screenshot 2024-12-23 041513](https://github.com/user-attachments/assets/c4ccf4dd-100c-4f38-a914-73b560209b53)

Since it is a public float, as we go back to Unity, we can adjust it in the Inspector when accessing the Ai object

![Screenshot 2024-12-23 041757](https://github.com/user-attachments/assets/fde2b894-d134-4872-9a36-dc6713fe534b)

As you can see, I have adjusted it to 3 as I would like my Ai to be a bit slower than my player.

Underneath that, I will add a private `Rigidbody`.
![Screenshot 2024-12-23 042111](https://github.com/user-attachments/assets/765ab61d-25d3-4375-83bd-b9cbe3698daf)

> This will enable physics for the player

Now we will go to the `Start void` and type in the rb component for the rigidbody
![Screenshot 2024-12-23 042129](https://github.com/user-attachments/assets/110b0382-d5d6-4d96-a93d-eb9f2578da7f)

After that, I would like to save the script and head back to Unity.

Since we want our player to lead the npc, we will use a tag method in the code. To connect the Ai script with the Player one, I will add a tag to the player and name it `Player`.
![Screenshot (365)q](https://github.com/user-attachments/assets/49e977f3-629f-4924-a80b-4b0f7b38ed61)


Having done this, we can return to Visual studio and add this line

![Screenshot 2024-12-23 042147](https://github.com/user-attachments/assets/b27de3f5-b978-4e70-ae8c-055bdbaa5495)

Later we will go to the Update void, because we want this action to be constantly updated by the computer
![Screenshot 2024-12-23 042823](https://github.com/user-attachments/assets/132a2824-6d0c-4c5d-8b36-6e87e7e18c6a)









