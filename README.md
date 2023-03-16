// 3D Texture 코드

let img;

function preload(){

  img = loadImage("rb.png");
  
}
function setup() {

  createCanvas(400, 400, WEBGL);
  
}

function draw() {

  background(220);
  
  rotateX(frameCount * 0.01);
  
  rotateY(frameCount * 0.01);
  
  rotateZ(frameCount * 0.01);
  
  texture(img);
  
  box(200);
  
}


//Eye Class 코드

var e1, e2, e3;

function setup() {

  createCanvas(640, 360);
  
  noStroke();
  
  e1 = new Eye( 250,  16, 120);
  
  e2 = new Eye( 164, 185,  80);  
  
  e3 = new Eye( 420, 230, 220);
  
}

function draw() {

  background(102);
  
  e1.update(mouseX, mouseY);
  
  e2.update(mouseX, mouseY);
  
  e3.update(mouseX, mouseY);

  e1.display();
  
  e2.display();
  
  e3.display();
  
}

function Eye(tx, ty, ts) {

  this.x = tx;
  
  this.y = ty;
  
  this.size = ts;
  
  this.angle = 0.0;

  this.update = function(mx, my) {
  
    this.angle = atan2(my-this.y, mx-this.x);
    
  }
  
  this.display = function() {
  
    push();
    
    translate(this.x, this.y);
    
    fill(255);
    
    ellipse(0, 0, this.size, this.size);
    
    rotate(this.angle);
    
    fill(153, 204, 0);
    
    ellipse(this.size/4, 0, this.size/2, this.size/2);
    
    pop();
    
  }
  
}

![무지개 3d](https://user-images.githubusercontent.com/119734977/225634093-784cc0ba-3de7-4a05-8988-0e33abaa5da9.PNG)
![눈동자 자바스크립트](https://user-images.githubusercontent.com/119734977/225634126-2afef92a-c16c-45fc-8c35-e198397f18d0.PNG)

