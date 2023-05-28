<!DOCTYPE html>
<html>
  <head>
    <title>Waving Sword Figure</title>
    <style>
      canvas {
        border: 1px solid black;
      }
    </style>
  </head>
  <body>
    <canvas id="myCanvas" width="400" height="400"></canvas>
    <script>
      const canvas = document.getElementById("myCanvas");
      const ctx = canvas.getContext("2d");
      
      const swordColor = "#c7b77e";
      const bodyColor = "#9dc3e6";
      const armColor = "#c5a36c";
      
      const bodyWidth = 50;
      const bodyHeight = 100;
      const armWidth = 20;
      const armHeight = 70;
      const swordWidth = 60;
      const swordHeight = 10;
      
      let armAngle = 0;
      
      function draw() {
        // Clear the canvas
        ctx.clearRect(0, 0, canvas.width, canvas.height);
        
        // Draw the body
        ctx.fillStyle = bodyColor;
        ctx.fillRect(canvas.width/2 - bodyWidth/2, canvas.height/2 - bodyHeight/2, bodyWidth, bodyHeight);
        
        // Draw the arm
        ctx.save();
        ctx.translate(canvas.width/2, canvas.height/2);
        ctx.rotate(armAngle);
        ctx.fillStyle = armColor;
        ctx.fillRect(-armWidth/2, -armHeight/2, armWidth, armHeight);
        
        // Draw the sword
        ctx.fillStyle = swordColor;
        ctx.fillRect(0, -swordHeight/2, swordWidth, swordHeight);
        
        ctx.restore();
        
        // Update the arm angle for the next frame
        armAngle += 0.05;
        
        // Request the next frame
        requestAnimationFrame(draw);
      }
      
      // Start the animation loop
      draw();
    </script>
  </body>
</html>
