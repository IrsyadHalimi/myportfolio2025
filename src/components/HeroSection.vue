<template>
  <section id="hero" class="h-screen bg-white text-black dark:bg-gray-900 dark:text-white transition-all flex items-center justify-center text-center w-full sm:px-8 md:px-16 lg:px-24">
    <div>
      <h1 class="text-5xl font-bold mb-4">Hello, I'm Irsyad</h1>
      <p class="text-xl">A Web Developer passionate about crafting beautiful web applications.</p>
      <a href="#projects">
        <button class="mt-6 px-6 py-3 bg-gray-900 text-white rounded hover:bg-gray-700 dark:bg-gray-700">
          View My Work
        </button>
      </a>
      <div
        ref="ball"
        class="ball"
        :style="ballStyle"
        @click="kickBall">
      </div>
    </div>
  </section>
</template>

<script>
export default {
    data() {
        return {
            position: { x:50, y:540 },
            speed: 2,
            rotation: 0,
        };
    },
    mounted() {
        this.moveBall();
    },
    methods: {
        moveBall() {
            this.position.x += this.speed;
            this.rotation += this.speed;

            if (this.position.x > window.innerWidth - 120 || this.position.x < 0) {
                this.speed = -this.speed;
            }

            requestAnimationFrame(this.moveBall);
        },
        kickBall() {
            this.speed += 5;
            setTimeout(() => {
                this.speed = 2;
            }, 5000);
        }
    },
    computed: {
        ballStyle() {
            return {
                position: 'absolute',
                left: `${this.position.x}px`,
                top: `${this.position.y}px`,
                width: '80px',
                height: '80px',
                backgroundImage: 'url(https://upload.wikimedia.org/wikipedia/commons/d/d3/Soccerball.svg)',
                backgroundSize: 'cover',
                borderRadius: '50%',
                transform: `rotate(${this.rotation}deg)`,
            };
        }
    }
};
</script>

<style scoped>
.ball {
    display: fixed;
    cursor: pointer;
    transition: transform 0.1s ease-out;
}
</style>