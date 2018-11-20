/**
 * Continuous Lines.
 *
 * Click and drag the mouse to draw a line.
 */

float x;
float y;
float px;
float py;
float easing = 0.08;

void setup() {
  size(1920, 1080);
  background(102);
  frameRate(120);
}

void draw() {

  float targetX = mouseX;
  float dx = targetX - x;
  x += dx * easing;
  float dpx = pmouseX - px;
  px += dpx * easing;

  float targetY = mouseY;
  float dy = targetY - y;
  y += dy * easing;
  float dpy = pmouseY- py;
  py += dpy * easing;

  float speed = abs(x-px) + abs(y-py);
  //if (speed < 30) {
  //  speed = 30;
  //}
  strokeWeight(speed);
  stroke(speed*3, random(speed,speed*3), random(speed*2,speed*3));

  if (mousePressed == true) {
    line(x, y, px, py);
  }
}
