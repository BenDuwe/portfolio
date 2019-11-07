<template>
  <div class="splash" v-bind:class="{ 'hide': $route.path !== '/' }">
    <div class="text">
      Hello, my name is
      <span class="highlight">Ben Duwé</span>.
      <br />I'm a junior web developer.
    </div>
    <button>
      <router-link to="/portfolio">
        View my projects
        <span class="btn-icon">
          <i class="fas fa-arrow-right"></i>
        </span>
      </router-link>
    </button>
    <canvas></canvas>
  </div>
</template>

<script>
export default {
  name: "Splash",
  props: {},

  mounted() {
    var canvas = document.querySelector("canvas");
    var splash = document.querySelector(".splash");

    canvas.width = window.innerWidth;
    canvas.height = splash.offsetHeight;

    var c = canvas.getContext("2d");
    // Animating
    var mouse = {
      x: undefined,
      y: undefined
    };

    window.addEventListener("mousemove", function(event) {
      mouse.x = event.x;
      mouse.y = event.y;
    });

    window.addEventListener("resize", resizeCanvas, false);
    window.addEventListener("orientationchange", resizeCanvas, false);

    function resizeCanvas() {
      canvas.width = window.innerWidth;
      canvas.height = splash.offsetHeight;

      init();
    }

    function Circle(x, y, dx, dy, radius) {
      this.x = x;
      this.y = y;
      this.dx = dx;
      this.dy = dy;
      this.radius = radius;
      this.minRadius = radius;
      this.maxRadius = radius * 9;
      this.color = "#cfcfcf";
      this.stroke = "rgba(255, 255, 255, 0.1)";

      this.draw = function() {
        c.beginPath();
        c.arc(this.x, this.y, this.radius, 0, Math.PI * 2, false);
        c.moveTo(this.x, this.y + this.radius);
        c.lineTo(this.x + 1300, this.y - 2000);
        c.strokeStyle = this.stroke;
        c.lineWidth = 1.5;
        c.stroke();

        c.fillStyle = this.color;
        c.fill();
      };

      this.update = function() {
        if (this.x + this.radius > innerWidth || this.x - this.radius < 0) {
          this.dx = -this.dx;
        }
        if (
          this.y + this.radius > splash.offsetHeight ||
          this.y - this.radius < 0
        ) {
          this.dy = -this.dy;
        }
        this.x += this.dx;
        this.y += this.dy;

        // interactivity
        if (
          mouse.x - this.x < 50 &&
          mouse.x - this.x > 0 //&&
        ) {
          this.stroke = "rgba(255, 255, 255, 0.4)";
        } else {
          this.stroke = "rgba(255, 255, 255, 0.1)";
        }

        this.draw();
      };
    }

    var circleArray = [];

    function init() {
      circleArray = [];
      if (window.innerWidth < 768) {
        for (var i = 0; i < 50; i++) {
          var radius = 0.3;
          var x = Math.random() * (innerWidth - 2 * radius) + radius;
          var y = Math.random() * (splash.offsetHeight - 2 * radius) + radius;
          var dx = Math.random() - 0.5;
          var dy = Math.random() - 0.5;
          circleArray.push(new Circle(x, y, dx, dy, radius));
        }
      } else {
        for (i = 0; i < 100; i++) {
          radius = 0.3;
          x = Math.random() * (innerWidth - 2 * radius) + radius;
          y = Math.random() * (splash.offsetHeight - 2 * radius) + radius;
          dx = Math.random() - 0.5;
          dy = Math.random() - 0.5;
          circleArray.push(new Circle(x, y, dx, dy, radius));
        }
      }
    }

    function animate() {
      requestAnimationFrame(animate);

      c.clearRect(0, 0, innerWidth, splash.offsetHeight);

      for (var i = 0; i < circleArray.length; i++) {
        circleArray[i].update();
      }
    }

    init();
    animate();
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
canvas {
  position: absolute;
  top: 0;
  left: 0;
  width: 100vw;
  background: #808080;
  z-index: -1;
}
.splash {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  position: relative;
  flex-grow: 1;
}
.hide {
  display: none;
}

.text {
  margin-bottom: 15px;
  font-size: 1.4rem;
}
.highlight {
  color: #42b983;
}

button {
  padding: 5px;
  border: 2px solid #c7c7c7;
  background: none;
}

button a {
  text-decoration: none;
  font-weight: bold;
  color: #2c3e50;
}
@media only screen and (min-width: 768px) {
  .text {
    font-size: 3rem;
  }
}
</style>
