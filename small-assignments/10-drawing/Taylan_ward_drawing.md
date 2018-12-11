boolean lightning=false;

//Position of cheeks
final int RIGHT_CHEEK_X = 425;
final int LEFT_CHEEK_X = 275;
final int CHEEK_Y = 290;


void setup() {
  size(700, 700);
  frameRate(50);
}

void draw() {
  background(0);
  drawPikachu();

  if (cheeks() || lightning) {
    lightningOn();
    lightningLeft();//3 bolts on the left.
    lightningLeft();
    lightningLeft();
    lightningRight();//3 bolts on the right.
    lightningRight();
    lightningRight();
  }
  else lightningOff();
}

void drawPikachu() {
  stroke(0);

  //Tail
  fill(0, 255, 255);
  rect(558, 460, 75, 30);
  fill(255, 0, 0);
  rect(452, 504, 150, 30);
  rect(512, 482, 30, 75);

  //Ears
  fill(0, 255, 255);
  triangle(391, 117, 461, 173, 610, 103);
  triangle(309, 117, 241, 173, 192, 15);

  //Ears, left then right.
  quad(240, 410, 241, 340, 205, 327, 190, 350);
  quad(463, 333, 463, 383, 510, 345, 485, 313);

  //Legs, left then right.
  rectMode(CORNER);
  rect(width/2-113, height*3/4, 50, 100);
  rect(width/2+63, height*3/4, 50, 100);

  //Body then head.
  rectMode(CENTER);
  rect(width/2, height/2+50, 226, 300);
  ellipse(width/2, height/3, 250, 250);

  //Cheeks, left then right.
  fill(255, 0, 0);
  ellipse(LEFT_CHEEK_X, CHEEK_Y, 50, 50);
  ellipse(RIGHT_CHEEK_X, CHEEK_Y, 50, 50);

  //Eyes, left then right.
  fill(0);
  ellipse(290, 220, 40, 50);
  ellipse(410, 220, 40, 50);

  //Nose
  triangle(width/2, 270, width/2+20, 260, width/2-20, 260);

  //Mouth
  line(width/2, 291, width/2+20, 300);
  line(width/2, 290, width/2-20, 300);
  line(width/2+20, 300, width/2+30, 290);
  line(width/2-20, 300, width/2-30, 290);
}

//Draws random bolt out lightning out of the left cheek.
void lightningLeft() {
  //Random shades of yellow.
  stroke(255, random(10, 26), 0);
  noFill();
  curve(random(width), random(height), LEFT_CHEEK_X, CHEEK_Y, 
  random(width), random(height), random(width), random(height));
}

//Draws random bolt of lightning out of the right cheek.
void lightningRight() {
  //Random shades of yellow.
  stroke(255, random(10, 26), 0);
  noFill();
  curve(random(width), random(height), RIGHT_CHEEK_X, CHEEK_Y, 
  random(width), random(height), random(width), random(height));
}

//Actions to run when lightning is on.
void lightningOn() {
  fill(255);
  //Pupils Centered
  ellipse(290, 220, 10, 10);
  ellipse(410, 220, 10, 10);
}

//Actions to run when lightning is off.
void lightningOff() {
  fill(0);
  //Pupils up.
  ellipse(290, 210, 10, 10);
  ellipse(410, 210, 10, 10);
}

//Returns true when the mouse hovers over Pikachu's cheeks.
Boolean cheeks() {
  int triggerDistance=25;
  if (dist(mouseX, mouseY, RIGHT_CHEEK_X, CHEEK_Y)<triggerDistance
    || dist(mouseX, mouseY, LEFT_CHEEK_X, CHEEK_Y)<triggerDistance) {
    return true;
  }
  else return false;
}

//Pressing any key flips the lightning "switch" on or off.
void keyPressed() {
  lightning = !lightning;
}
