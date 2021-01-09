<template>
  <div id="app">
    <svg-sprite />
    <h1>
      Vue SVG Icon Demo
      <svg-icon icon="fire" />
    </h1>
    <div>
      <ul>
        <li v-for="feature in $options.list" :key="feature">
          <svg-icon icon="badge-check" />
          {{ feature }}
        </li>
      </ul>
    </div>
    <button>
      Send
      <svg-icon icon="send" />
    </button>
    <p class="please-wait">
      <svg-icon icon="cog-solid" spin></svg-icon>
      Processing &hellip;
    </p>
    <p class="warning">
      <svg-icon icon="exclamation" />
      Something went wrong.
    </p>
    <p>
      <svg-icon icon="love" allow-fill />
      The heart SVG is using its own <code>fill</code> color!
    </p>
    <p>
      <svg-icon icon="gradient" allow-fill />
      This SVG has `defs`
    </p>
  </div>
</template>

<script>
import SvgIcon from '@/components/SvgIcon.vue'
import SvgSprite from '@/components/SvgSprite.vue'

export default {
  name: 'App',
  components: {
    SvgIcon,
    SvgSprite,
  },
  list: [
    'Easy to add or remove icons',
    'No icon font required',
    'Simple syntax',
  ]
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  font-size: 16px;
  font-weight: 500;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  max-width: 768px;
  margin: auto;
}
@media (min-width: 768px) {
  #app {
    font-size: 24px;
  }
}

/* Icon Styling */
h1 .icon {
  color: orange;
}
.please-wait .icon {
  opacity: 0.3;
}
li .icon {
  color: deeppink;
}
button .icon {
  margin-left: 0.5ch;
  color: deepskyblue;
}
.warning .icon {
  font-size: 1.5em;
  margin-right: 0.25em;
  color: darkorange;
}

/* Boring Stuff */
ul {
  display: inline-block;
  list-style-type: none;
  padding: 0;
  text-align: left;
  margin: 0 auto 1em 0;
}
li + li {
  margin-top: 0.25em;
}

button {
  color: white;
  font-size: 1em;
  padding: 0.5em 1em;
  background: #667;
  border: 0;
  border-bottom: 2px solid deepskyblue;
  border-radius: 4px;
  outline: none;
}
button:hover {
  background: #778;
}

.please-wait, .warning {
  padding: 1em;
}
.please-wait {
  color: darkslategray;
  background: paleturquoise;
  border-radius: 8px;
}

.warning {
  border-left: 4px solid darkorange;
  background: lemonchiffon;
  color: saddlebrown;
}
</style>
