<template>
  <div class="splash anchor">
    <a name="splash"></a>
    <div class="text">
      Hi, my name is
      <span class="highlight">Ben Duwé</span>.
      <br />I'm a junior web developer.
    </div>
    <div>
      <button>
        <a href="#about">About me</a>
      </button>
      <button>
        <a href="#portfolio">My projects</a>
      </button>
    </div>
    <a href="#about">
      <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24">
        <path
          d="M0 7.33l2.829-2.83 9.175 9.339 9.167-9.339 2.829 2.83-11.996 12.17z"
          fill="#2C383B"
        />
      </svg>
    </a>
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

    canvas.width = splash.offsetWidth;
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
      this.color = "rgba(75, 192, 176, 0.4)";
      this.stroke = "rgba(75, 192, 176, 0.4)";

      this.draw = function() {
        c.beginPath();
        //c.arc(this.x, this.y, this.radius, 0, Math.PI * 2, false);
        c.moveTo(this.x, this.y + this.radius);
        c.lineTo(this.x + 1300, this.y - 2000);
        c.strokeStyle = this.stroke;
        c.lineWidth = 1.3;
        c.stroke();

        // c.fillStyle = this.color;
        // c.fill();
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
          this.stroke = "rgba(75, 192, 176, 0.4)";
        } else {
          this.stroke = "rgba(75, 192, 176, 0.1)";
        }

        this.draw();
      };
    }

    var circleArray = [];

    function init() {
      circleArray = [];
      if (window.innerWidth < 768) {
        for (var i = 0; i < 50; i++) {
          var radius = 0.2;
          var x = Math.random() * (innerWidth - 2 * radius) + radius;
          var y = Math.random() * (splash.offsetHeight - 2 * radius) + radius;
          var dx = Math.random() - 0.5;
          var dy = Math.random() - 0.5;
          circleArray.push(new Circle(x, y, dx, dy, radius));
        }
      } else {
        for (i = 0; i < 100; i++) {
          radius = 0.2;
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
  background: rgb(244, 246, 247);
  z-index: -1;
}
.splash {
  color: #2c383b;
  font-style: italic;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  position: relative;
  height: calc(100vh - 3.9375em);
  /* width: 100vw; */
  /* border-bottom: 2px solid #2c383b; */
}
svg {
  height: 50px;
  width: 50px;
  position: absolute;
  bottom: 3rem;
  left: 50%;
  transform: translateX(-50%);
}
.hide {
  display: none;
}

.text {
  margin-bottom: 15px;
  font-size: 1.4rem;
}
.highlight {
  color: #ff312e;
}

button {
  margin: 10px;
  padding: 5px 0;
  width: 6rem;
  border: 2px solid #8b2635;
  background: none;
}

button a {
  text-decoration: none;
  font-weight: bold;
  color: #2c383b;
}
@media only screen and (min-width: 768px) {
  .text {
    font-size: 3rem;
  }
}
</style>
