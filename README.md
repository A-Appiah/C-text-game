# C-text-game
This is a simple choose your own adventure based text game. Feel free to add any changes to make it your own! Its run off of Unity - since I haven't made $100,000, no need to give Unity credit :)

using UnityEngine;
using UnityEngine.UI;
using System.Collections;

public class TextController : MonoBehaviour {
	public Text text;
	private enum States {cell, a_1, officer, b_1, riot, b_3, c_1, c_2, c_3, c_4, c_5, c_6, c_7, c_8, c_9, c_10, escape}
	private States myState;
	// Use this for initialization
	void Start () {
		myState = States.cell;
	}
	
	// Update is called once per frame
	void Update () {
			print (myState);
			if (myState == States.cell) {
				state_cell ();
			} else if (myState == States.a_1) {
				state_a_1();
			} else if (myState == States.officer) {
				state_officer();
			} else if (myState == States.b_1) {
				state_b_1();
			} else if (myState == States.riot) {
				state_riot();
			} else if (myState == States.b_3) {
				state_b_3();
			} else if (myState == States.c_1) {
				state_c_1();
			} else if (myState == States.c_2) {
				state_c_2();
			} else if (myState == States.c_3) {
				state_c_3 ();
			} else if (myState == States.c_4) {
				state_c_4 ();
			} else if (myState == States.c_5) {
				state_c_5();
			} else if (myState == States.c_6) {
				state_c_6();
			}
			}
		
		void state_cell () {
				text.text = "You wake up in a prison cell. Not knowing how you got there - only that you must get out \n\n " +
							"Press A to look around the cell";
				
				if (Input.GetKeyDown(KeyCode.A)) {
					myState = States.a_1;
					}		
				}
		
		
		void state_a_1 () {
				text.text = "You roam around your cell observing anything irregular, hoping to find a way to escape \n\n" +
							"Press A to shout let me out! \n\n" +
							"Press B to look at the other cells \n\n" +
							"Press C to look out the window";
		
				if (Input.GetKeyDown(KeyCode.A)) {
					myState = States.officer;
				} else if (Input.GetKeyDown(KeyCode.B)) {
					myState = States.b_1;
				} else if (Input.GetKeyDown(KeyCode.C)) {
					myState = States.c_1;
				}
			}
			
		void state_officer () {
				text.text = "A police officer hears your cries for help. He walks directly up to your cell. He looks you " +
							"straight in the eyes and says SHUT UP! There is no escaping here! He then bangs his baton " +
							"on your cell bars in a attempt to scare you and make you jump back. \n\n" +
							"Fucking asshole - you think to yourself.\n\n" +
							"Press R to keep looking around the cell";
							
				if (Input.GetKeyDown(KeyCode.R)) {
					myState = States.a_1;
				}
				
			}
	
		void state_b_1 () {
				text.text = "You walk up to the front of the cell, looking into the cells of other inmates. A certain bald " +
							"headed inmate across the hallway, with tattoos covering his entire face catches your eye. " +
							"He has something in hishand, but you can't see what it is. The distance is too far for you " +
							"too see what it is, so he simply spells it out with his hands - RIOT \n\n" +
							"Press B to continue";
				
				if	(Input.GetKeyDown(KeyCode.B)) {
					myState = States.riot;
					}
				}
				
		void state_riot () {
				text.text = "During lunch, everyone is tense in the cafeteria. The tension could be cut with a butter knife " +
							"The bald tattooed inmate from earlier spots you, then comes and sits with you. Are you ready? " +
							"he says. You look him nerviously in the eye then say yes. Suddenly the jungle becomes a zoo. " +
							"inmates viciously attack other inmates. Nows our chance says the fellow inmate - Lets move! \n\n" +
							"Press B to continue";
				
				if (Input.GetKeyDown(KeyCode.B)) {
					myState = States.b_3;
					}	
							 
				}
				
		void state_b_3 () {
				text.text = "You and your new found friend attempt to escape while the guards are occupied. You both locate " +
							"the main control room and break in - hoping to open all the cell doors and the main prison gates." +
							"You open the main prison gates and immediately both of you sprint towards your freedom. " +
							"Before you reach the prison's front gates, you hear a crack and suddenly you fall to the ground. " +
							"Things begin to go dark - before you loose concious you're suddenly surrounded by guards. " +
							"One of them must've shot you - you think to yourself.. Then everything goes dark and you die at the " +
							"prisons gates. \n\n" +
							"Press R to Restart";
							
				if (Input.GetKeyDown(KeyCode.R)) {
					myState = States.cell;
				}
				
			}
		
		void state_c_1 () {
				text.text = "You look out the window, thinking about your previous freedom. You grab at the bars and sigh " +
							"pretending to pull the bars off, you successfully pull one completely off. You think, this is " +
							"my chance to escape! You put the bar back in place thinking about trying to escape during the " +
							"night.\n\n" +
							"Press C to continue";
				
				if (Input.GetKeyDown(KeyCode.C)) {
					myState = States.c_2;
					}	
				}
				
		void state_c_2 () {
				text.text = "Once night falls, you jump out of bed and immediately start working at the loose bars on the " +
							"windows. Surprisingly, the bars come off fairly easy. You manage to pry three bars loose. Now " +
							"is the moment of truth. You manage to pop off the window, and you jump out. You're now outside, " +
							"and it's freezing, but that is a thought for later. Do you decide to jump the prison's fence or " +
							"do you decide to head to the bus yard \n\n" +
							"Press F to climb the fence \n\n" +
							"Press Y to head to the bus yard";
				
				if (Input.GetKeyDown(KeyCode.F)){
						myState = States.c_3;
					} else if (Input.GetKeyDown(KeyCode.Y)) {
						myState = States.c_4;
					}	
				}
		
		void state_c_3 () {
				text.text = "You start heading towards the fence, making sure that no guards are around. You near the fence, " +
							"you then tap it to make sure it's not electric. Surprisingly, it doesn't shock you. You begin " +
							"your climb to the top. Half way to the top a loud bang cracks the air. You feel weak suddenly, " +
							"and you fall from the fence. You look down and see you've been shot. Slowly everything goes " +
							"dark and you die in your vail attempt at escacpe. \n\n" +
							"Press R to Refresh";
				if (Input.GetKeyDown(KeyCode.R)) {
						myState = States.cell;
						}			
					}
					
		void state_c_4 () {
				text.text = "You make your way to the bus yard, and now you're faced with another difficult decision - " +
							"steal a bus and drive straight out of this place, or hide underneath one of the buses. \n\n" +
							"Press H to steal the bus \n\n" +
							"Press X to hide under the bus";
					
					if (Input.GetKeyDown(KeyCode.H)) {
						myState	= States.c_5;
						} else if (Input.GetKeyDown(KeyCode.X)) {
						myState = States.c_6;
						}
					}
		
		void state_c_5 () {
				text.text = "You decide stealing a bus is the best idea. You hop inside of a random bus, and to your " +
							"surprise - there is a pair of keys in the ignition. You immediately hop in the drivers seat " +
							"and start the bus. This sets the prison on high alert. You step on the gas and head towards the " +
							"front gates. The watchtowers have their high beams set right on you, practically blinding you. " +
							"Suddenly the glass cracks and you feel a sharp pain in your chest - Snipers - you think in your " +
							"head. You feel the blood flowing from your chest, and you suddenly start loosing concious. The bus " +
							"plows through the prison's front gates. By the time reaches the outskirts of the prison, the officers " +
							"approach the bus only to find you slumped over the steering wheel and dead from the snipers bullet. \n\n" +
							"Press R to Restart";
							
					if (Input.GetKeyDown(KeyCode.R)) {
						myState = States.cell;
						}
					}
					
		void state_c_6 () {
				text.text = "You decide hiding under the bus is the best idea. You open the trunk of the bus and hop in " +
							"hoping that you won't be found. Surprisingly, you wake up in the trunk of the bus - only to " +
							"discover that the bus is one the move. Then it hits you, you did it! You escaped the prison!\n\n" +
							"Congrats on beating the game!\n\n" +
							"Press R to start the game over";
					
					if (Input.GetKeyDown(KeyCode.R)) {
						myState = States.cell;	
						}
					}
			}

