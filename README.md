# 3dchessboard
3d chessboard in p5js
https://benjaminfox1.github.io/3dchessboard/

I started in 2d with experimenting with for loops to create a chessboard and ended up seeing if I could translate it into 3d using WEBGL. 

<details><summary>Code Below</summary>
<p>
  
```JavaScript
  
  //3d Chessboard

var x;
var y;
var square;

var my3d;

function setup() {
  createCanvas(800, 800,WEBGL);
  x=width/8;
  y=height/8;

  my3d=0.05

  square = {
    xpos: x,
    ypos: y,
    size: x
  }
}

function draw () {
  background(255);
  
  fill(200)
  rotateX(my3d);
  rotateY(my3d);
  rotateZ(my3d+3);
  
  translate(-400,-400,0);

  fill(0);
  for(let i=0; i<9; i++){
    line(0, y*i, width, y*i);
    line(x*i, 0, x*i, height);

    rect(square.xpos*2*i+x, square.ypos-y, square.size, square.size);
    rect(square.xpos*2*i, square.ypos-y+y, square.size, square.size);

    rect(square.xpos*2*i+x, square.ypos+y, square.size, square.size);
    rect(square.xpos*2*i, square.ypos+y+y, square.size, square.size);

    rect(square.xpos*2*i+x, square.ypos+y+y+y, square.size, square.size);
    rect(square.xpos*2*i, square.ypos+y+y+y+y, square.size, square.size);

    rect(square.xpos*2*i+x, square.ypos+y+y+y+y+y, square.size, square.size);
    rect(square.xpos*2*i, square.ypos+y+y+y+y+y+y, square.size, square.size);
  }

  my3d=my3d+0.002;
}
```
  
 </p>
</details>
