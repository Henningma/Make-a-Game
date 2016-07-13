# Make-a-Game
My first game creation

Okay, I hope this is a readme.

Am using unity 5.3.5f personal, am not sure this is imortant to know but here it is.

First am making a ball that is a playable players. first it's only me to play the game.
Second am making a floor that is ground. that is used for the ball to walke on. if you walke over you will fall.
Third am making Js - java script that is controling the ball, floor and other stuff in the game.
All this is working, made in unity and windows.

Am done making a ball, floor and script, but the control is not working as it should in 5.3.5.
I looked at a video course called "make a game" by brackeys.com, but he used unity 4.2.x. so that version using different code then unity 5.3.5. So here I need help to fix it.

Here is the code if off interest.
#pragma strict

var rotationSpeed = 100;
var jumpHeight = 8;

private var isFalling = false;

function Update ()
{
	//Handle ball rotation.
	var rotation : float = Input.GetAxis ("Horizontal") * rotationSpeed;
	rotation *= Time.deltaTime;
	GetComponent.<Rigidbody>().AddRelativeTorque (Vector3.back * rotation);
	
	if (Input.GetKeyDown(KeyCode.W) && isFalling == false)
	{
		GetComponent.<Rigidbody>().velocity.y = jumpHeight;
	}
	isFalling = true;
}

function OnCollisionStay ()
{
	isFalling = false;
}

