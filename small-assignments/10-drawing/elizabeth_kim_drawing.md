void setup() {
size(700,700);
 background(179, 213, 216);
line(270,520,580,550);
    fill(136, 142, 150);
ellipse(270,370,200,400);  
arc(180,600,100,80,PI,TWO_PI,CHORD);
arc(360,600,100,80,PI,TWO_PI,CHORD);
ellipse(130,60,120,120);
ellipse(320,70,130,130);
triangle(130,60,340,70,110,360);
    fill(0);
ellipse(100,160,30,30);
ellipse(210,170,30,30);
}

void draw() {
  stroke(225);
  noFill();
ellipse(mouseY,mouseX,20,20);

}
