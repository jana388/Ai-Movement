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

After this, we will add a C# script and name it `AiMovement`

![Screenshot 2024-12-23 002647](https://github.com/user-attachments/assets/7c1fd53a-6e04-4a73-92b6-732939f17a7f)

Great, now we can open the script in the Microsoft Visual Studio.

The first thing we will do is erase first two lines of code because we will not need to use these two engines to run this code.

![Screenshot 2024-12-23 003531](https://github.com/user-attachments/assets/95bd70e9-d415-4d1b-bc53-c147593c8250)



Because our Ai is not controlled by an input, we need to inform the computer what will give npc the directions. 




as an example, we can add a cube for the ai so we can test the code
simply add a 3d object to the scene, add a rigidbody as a component and a c# script

then we can open a script and add our code
