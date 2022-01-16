<template>
  <div>
    <div class="slider">
      <div
        class="slide"
        :style="sliderPosition"
        v-for="({ title, content }, index) in slides"
        :key="index"
      >
        <h3>{{ title }}</h3>
        <p>{{ content }}</p>
      </div>
      <div class="actions">
        <button class="actions-button" :disabled="start" @click="prev()">
          <svg
            xmlns="http://www.w3.org/2000/svg"
            height="18px"
            viewBox="0 0 24 24"
            width="18px"
            fill="#FFF"
          >
            <path d="M15.41 7.41L14 6l-6 6 6 6 1.41-1.41L10.83 12z" />
          </svg>
        </button>
        <button class="actions-button" :disabled="end" @click="next()">
          <svg
            xmlns="http://www.w3.org/2000/svg"
            height="18px"
            viewBox="0 0 24 24"
            width="18px"
            fill="#FFF"
          >
            <path d="M10 6L8.59 7.41 13.17 12l-4.58 4.59L10 18l6-6z" />
          </svg>
        </button>
      </div>
    </div>
    <div class="dots">
      <div
        v-for="(row, index) in slidesLength"
        :key="index"
        class="dot"
        @click="goToSlide(index)"
        :class="{ active: activeDot(index) }"
      />
    </div>
  </div>
</template>

<script >
export default {
  name: 'Slider',
  data() {
    return {
      activeSlide: 0,
    }
  },
  props: {
    slides: Array,
  },
  computed: {
    sliderPosition() {
      return {
        transform: `translateX(-${this.activeSlide}00%)`,
      }
    },
    slidesLength() {
      return this.slides.length
    },
    start() {
      return this.activeSlide === 0
    },
    end() {
      return this.activeSlide === this.slidesLength - 1
    },
  },
  methods: {
    activeDot(index) {
      return this.activeSlide === index
    },
    goToSlide(index) {
      this.activeSlide = index
    },
    prev() {
      if (this.start) return null
      this.activeSlide--
    },
    next() {
      if (this.end) return null
      this.activeSlide++
    },
  },
}
</script>

<style scoped>
.slider {
  position: relative;
  display: flex;
  flex-wrap: nowrap;
  flex-direction: row;

  max-width: 100%;
  overflow: hidden;
}
.slide {
  min-width: 100%;
  max-width: 100%;
  transition: all 0.35s ease;
  text-align: center;
  padding: 0 2.5rem;

  /* Allow .slider to be smaller then it's nowrapped content */
  width: 0;
}
.dots {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: row;
  gap: 0.5rem;
}
.dot {
  cursor: pointer;
  height: 10px;
  width: 10px;

  border-radius: 5px;
  background-color: #ccc;
}
.dot.active {
  width: 20px;
  background-color: var(--color-primary);
}
.actions {
  position: absolute;
  display: flex;
  justify-content: space-between;
  align-items: center;
  width: 100%;
  top: 0;
  bottom: 0;
}
.actions-button {
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 0.25rem;

  line-height: 1;
  cursor: pointer;
  border-radius: 50%;
  background-color: #ccc;
  opacity: 0.5;
}
.actions-button:hover,
.actions-button:focus {
  background-color: var(--color-primary);
  opacity: 0.8;
}
.actions-button[disabled] {
  opacity: 0.1 !important;
  transition: all 0.35s ease;
}
</style>