# Shooting-Code
Totorial for spawning bullets when trying to shoot
1.	Create unity scene

•	First you need to create a unity scene
•	In the unity scene you need to create an empty object and set it as the child for character you want to shoot, in the position you want to shoot from
•	The empty object will serve as the position where the bullets will be spawned (ex. Tip of gun) so you can rename it FirePoint
•	You will also need to create a prefab for your bullet, the object that will be spawned as a bullet
•	When this is done, create a script and add it to your character

2.	Within the script

•	To begin with you need to create references for the position of the fire point and the object that will spawn as bullet


using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class Shoot : MonoBehaviour
{
public Transform FirePoint;
public GameObject Bullet;


•	When this is done, save it, go to unity and drag and drop the FirePoint from in unity scene in the transform space created in the script component as well as the bullet prefab in the script component in the bullet box
•	If you don’t do that, the script will not know what to spawn and where to spawn and therefor won’t work
•	We don’t need to write anything in the Void Start so we can just skip to Void Update
•	In Void Update we will create a simple if statement

    void Update()
    {
        if(Input.GetButtonDown("Fire1")) 
		{
            Instantiate(Bullet, FirePoint.position, FirePoint.rotation); 
		}
    }
•	These are simple statements, and they mean:
 	if(Input.GetButtonDown("Fire1")) = if player presses button set as Fire1
 	Instantiate = spawn
 	(Bullet, FirePoint.position, FirePoint.rotation) = the bullet prefab, at the location of Firepoitn, at the rotation of Firepoint

If you go in unity and play the game, you can press left click and left ctrl to spawn your bullets

3.	Customization 

•	By default Fire 1 is left click and left control 
•	if you want to change the input for "Fire1" you can go to EDIT> PROJECT SETTING > INPUT MANAGER >AXES > FIRE 1 and you can make fire 1 be any button you want
