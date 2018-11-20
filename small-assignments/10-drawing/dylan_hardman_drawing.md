// Canvas size
size(1000, 1000);
background(216, 253, 255);

// Landscape
fill(237, 234, 225);
quad(0, 1000, 250, 400, 750, 400, 1000, 1000);

// Tree
fill(0);
rect(700, 350, 10, 50);
fill(24, 73, 11);
triangle(600, 350, 700, 100, 800, 350);

// Snowman Body
fill(255, 255, 255);
ellipse(500, 350, 200, 200);
ellipse(500, 550, 275, 275);
ellipse(500, 800, 350, 350);
line(425, 500, 300, 400);
line(600, 525, 675, 650);

// Snowman Hat
fill(0);
stroke(0);
line(375, 250, 650, 300);
quad(465, 175, 600, 200, 580, 290, 445, 265);
fill(0);
stroke(0);

//Snowman Face
ellipse(520, 325, 20, 40);
ellipse(480, 325, 20, 40);
arc(500, 375, 40, 30, 0, PI, CHORD);

// Snowman Buttons
ellipse(500, 475, 20, 20);
ellipse(500, 525, 20, 20);
ellipse(500, 575, 20, 20);
