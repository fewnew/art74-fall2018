
https://editor.p5js.org/katpro13/sketches/B1qDXopAX


function setup() {
  createCanvas(800, 600, WEBGL);
}
function draw(){

  if(mouseIsPressed){
    fill(255,207,17);
  } else {
    fill(73,135,76);
  }
  
  ellipse(mouseX,mouseY,80,80);
  if (keyIsPressed === true) {
    fill(27,132,50);
  }else {
    fill(25,0,51);
  }
 rect(25,9,25,51);
  fill(45,173,45)
  sphere(50);
}

