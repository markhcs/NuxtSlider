<template>
  <main>
    <div class="content">
      <h1>Nuxt Slider</h1>
      <CommonSlider :slides="slides" />
    </div>
  </main>
</template>

<script>
export default {
  data() {
    return {
      slides: [
        {
          title: 'Lorem ipsum?',
          content:
            'Sed at dui nec erat venenatis rutrum id bibendum neque. Maecenas mollis scelerisque ligula, ullamcorper rutrum elit finibus vitae. ',
        },
        {
          title: 'Dolor sit amet?',
          content:
            'Praesent cursus semper varius. Morbi sed quam nec felis sagittis maximus. Suspendisse potenti. Maecenas sagittis orci sit amet felis pretium consequat.',
        },
        {
          title: 'Consectetur?',
          content:
            'Aenean sit amet risus magna. Mauris risus ipsum, ultrices vel lorem a, congue placerat nisi. Suspendisse accumsan euismod dolor in porttitor.',
        },
        {
          title: 'Adipiscing elit?',
          content:
            'Donec ultrices non tellus eu tempor. Sed ultrices eget tellus eu bibendum. Ut pulvinar est in sollicitudin molestie. In hac habitasse platea dictumst. Nunc iaculis tincidunt sagittis. Nam gravida velit et tellus sodales mattis.',
        },
        {
          title: 'Suspendisse?',
          content:
            'Vivamus ultrices massa nec congue gravida. Pellentesque euismod sapien eu diam vestibulum lobortis. Cras pretium mollis odio, vel pharetra est sollicitudin ut. Nam vulputate quam sodales erat placerat, vel consectetur enim pulvinar.',
        },
      ],
    }
  },
}
</script>

<style>
:root {
  --font-size: 0.9rem;
  --color-text: #000;
  --color-primary: hotpink;
}
@media only screen and (min-width: 1000px) {
  :root {
    --font-size: 1rem;
  }
}

*,
*:before,
*:after {
  box-sizing: border-box;
}

html {
  font-size: var(--font-size);
}

body {
  color: var(--color-text);
  font-family: -apple-system, BlinkMacSystemFont, Segoe UI, Roboto, Oxygen,
    Ubuntu, Cantarell, Fira Sans, Droid Sans, Helvetica Neue, sans-serif;
  font-size: 1rem;
  line-height: 1.4;

  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
main {
  display: flex;
  justify-content: center;
  align-content: center;
  flex-direction: column;
  min-height: 100vh;
}
.content {
  width: 100%;
  max-width: 800px;
  padding: 0 0.5rem;
  margin: 0 auto;
}
img {
  width: 100%;
  height: auto;
}
a {
  color: inherit;
  color: var(--color-primary);
}
a:hover,
a:focus {
  color: var(--color-primary-hover);
}
h1 {
  font-size: 2.5rem;
  line-height: 1.4;
  text-align: center;
}
p {
  font-size: 1.1rem;
  line-height: 1.6;
}
button {
  all: unset;
}
</style>