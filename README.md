# game
It is optional, which means I don't have to do it. 

int x = 385; // x for you
int y = 780; // y for you
int objex = 400 ; // x for obstacle 0
int gox = 800 ; // x for returning obstacle
boolean gameover = true; // gameover
int objey = 0  ; // y for obstacle 0
int goy = 800; // y for return obstacle 0 
int obstax = 0; // x for obstacle 1
int obstay = 0; // y for obstacle 1
int obstax2 = 800; // x for return obstacle 1
int obstay2 = 800; // y for return obstacle 1


void setup () {
  size(800, 800); // size
}   


void draw () {
  if (gameover==true) {  // gameover is true 
    background(0); // black background
    fill(255); // white rectangles
    rect(400, objey, 40, 40); // vertical rectangle 1
    objey=objey+5; // moving by 5
    rect(400, goy, 20, 20);  // return vertical rectangle 1
    
    rect(obstax, obstay, 40, 40);  // diagnol rectangle  2
    obstax=obstax+4; // moving speed x
    obstay=obstay+4; // moving speed y
    rect(obstax2,obstay2,40,40);  // return diagnol rectangle 2
    rect(objex, objey, 40, 40); //  diagnol rectangle 1
    rect(gox, goy, 40, 40); // return diagnol rectangle 1

    rect(objex, objey, 40, 40);
    rect(gox, goy, 40, 40);
    rect(x, y, 20, 20); // you
    if (keyPressed) {
      if (key=='w') {
        y=y-10;
      }
      if (key=='a') {
        x=x-10;
      }
      if (key=='s') {
        y=y+10;
      }
      if (key=='d') {
        x=x+10;
      }
    }
    rect(objex, 400, 20, 20); // obstacle 1
    objex=objex+5;
    if (objex>780) {
      rect(gox, 400, 20, 20); // return obstacle 1
      gox=gox-5;
    }
  
  if (y>400+10) { // return crash course collison
  } else {
    if (y<400-10) {
    } else { 
      if (x>gox+10) {
      } else {
        if (x<gox-10) {
        } else {
          background(255, 0, 0);  // returning end 
          gameover=false;
          textSize(32);
          text("Game Over, press r to try again", 0, 400);
        }
      }
    }
  }  
  if (y>400+12) { //  crash course collision
  } else {
    if (y<400-12) {
    } else { 
      if (x>objex+12) {
      } else {
        if (x<objex-12) {
        } else {
          background(255, 0, 0); // end
          gameover=false;
          fill(0);
          textSize(32);
          text("Game Over, press r to try again", 0, 400);
        }
      }
    }
  }
  if (gox<20) { // bounce
    objex=0;
    gox=801;
  }

  if (objey>780) {
    goy=goy-5;
  }
  if (goy<20) {
    objey=0;
    goy=801;
  }



  if (y>goy+15) { // return crash course collison
  } else {
    if (y<goy-15) {
    } else { 
      if (x>400+15) {
      } else {
        if (x<400-15) {
        } else {
          background(0, 0, 0);  // returning end 
          gameover=false;
          fill(255);
          textSize(32);
          text("Game Over, press r to try again", 0, 400);
        }
      }
    }
  }  
  if (y>objey+15) { //  crash course collision
  } else {
    if (y<objey-15) {
    } else { 
      if (x>400+15) {
      } else {
        if (x<400-15) {
        } else {
          background(0, 0, 0); // end
          gameover=false;
          fill(255);
          textSize(32);
          text("Game Over, press r to try again", 0, 400);
        }
      }
    }
  }



  if (y>goy+5) { // return crash course collison
  } else {
    if (y<goy-5) {
    } else { 
      if (x>gox+5) {
      } else {
        if (x<gox-5) {
        } else {
          background(0, 0, 0);  // returning end 
          gameover=false;
          fill(255);
          textSize(32);
          text("Game Over, press r to try again", 0, 400);
        }
      }
    }
  }  
  if (y>objey+5) { //  crash course collision
  } else {
    if (y<objey-5) {
    } else { 
      if (x>objex+5) {
      } else {
        if (x<objex-5) {
        } else {
          background(0, 0, 0); // end
          gameover=false;
          fill(255);
          textSize(32);
          text("Game Over, keep r pressed to try again", 0, 400);
        }
      }
    }
  }
  if(obstax>800) {
   obstax2=obstax2-4; 
  }
  if(obstay>800) {
   obstay2=obstay2-4; 
  }
  if(obstay<0) {
   obstay=10; 
  }
  if(obstax2<0) {
   obstax=0; 
 obstax2=801;
  }
  if(obstay2<0) {
   obstay=0;
   obstay2=801;
  }
  
  
  
  
 
 
  }
      if (keyPressed) {
    if (key=='r') {
      gameover=true;
      x=385;
      y=780;
      objex=400;
      objey = 400;
      gox=400;
      goy=400;
    }
  }
}
