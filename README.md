# MidpointFindingKarel
Stanford Computer Science Department (CS106A): Goal of this algorithm is to have Karel find the center of the 
grid she's placed on. Created by BRYAN PACHECO.
/*
 * File: MidpointFindingKarel.java
 * -------------------------------
 * When you finish writing it, the MidpointFindingKarel class should
 * leave a beeper on the corner closest to the center of 1st Street
 * (or either of the two central corners if 1st Street has an even
 * number of corners).  Karel can put down additional beepers as it
 * looks for the midpoint, but must pick them up again before it
 * stops.  The world may be of any size, but you are allowed to
 * assume that it is at least as tall as it is wide.
 */

import stanford.karel.*;

public class MidpointFindingKarel extends SuperKarel {

	// You fill in this part

	public void run() {
		putBeeper();
		putLastBeeper();
		put1MoreBeepers();
		move();
		putNextBeeper();
		move();
		putNextBeeper();
		move();
		putNextBeeper();
		move();
		putNextBeeper();
		move();
		putNextBeeper();
		move();
		putBeeper();
		eraseBeepersToLeft();
		cleanRightToCenter();
		returnToCenter();
	}
	
	/* this new method i created called putLastBeeper is so that Karel places a beeper at the
	 * east bottom corner in order for him to start figuring out where the center is*/
	
	
	private void putLastBeeper() {
		while (frontIsClear()){
			move();
		}
			turnAround();
			putBeeper();
			move();
	}
	
	/* This algorithm explains how Karel knows to add one more beeper in front of every beeper until his in the middle*/
	
	
	private void put1MoreBeepers(){
		while (noBeepersPresent()){
			move();
		}
		turnAround();
		move();
		putBeeper();
		

		/* This algorithm explains how Karel knows to add one more beeper in front of every beeper until his in the middle*/
		
	}
		private void putNextBeeper() {
			while (noBeepersPresent()){
				move();
			}
			turnAround();
			move();
			putBeeper();
		}
		
		/* the folllowing method explains how Karel knows to clean all the beepers to the left of the center one*/
		
		private void eraseBeepersToLeft() {
			move();
			
			if (beepersPresent()) {
				pickBeeper();
				move();
				pickBeeper();
				move();
				pickBeeper();
				move();
				pickBeeper();
				turnAround();
				
			}
			/* the folllowing method explains how Karel knows to clean all the beepers to the right of the center one*/
				}
		private void cleanRightToCenter() {
			while (noBeepersPresent()) {
				move();
			}
			move();
			pickBeeper();
			move();
			pickBeeper();
			move();
			pickBeeper();
			move();
			pickBeeper();
			
			
			/* after all beepers to left and right were cleaned, he returned to the middle where the last beeper was and faced back east*/
		}
		private void returnToCenter() {
			turnAround();
			while (noBeepersPresent()) {
				move();
				
			}
			turnAround();
		}
}

	
	
		



