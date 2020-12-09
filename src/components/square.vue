<template>
  <a v-bind:href="href" transition="expand"  class="square rounded-lg shadow-md" :style="cssVars" v-bind:class="size">
    <h2 v-if="!!text" v-html="text" class="text-3xl"></h2>
    <p v-if="!!description" v-html="description"></p>
  </a>
</template>

<script>
export default {
  name: 'Square',
  props: {
    color: String,
    size: String,
    href: String,
    text: String,
    description: String,
    bgColor: {
      type: String,
      default: "#0099CC"
    },
    height: {
      type: Number,
      default: 400
    }
  },
  computed: {
    cssVars() {
      return {
        '--bg-color': this.bgColor,
        '--height': this.height + 'px',
        '--text-color': this.color
      }
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .square {
    background-color: var(--bg-color);
    color: var(--text-color);
    height: var(--height);
    margin: 10px;
    display: flex;
    flex-direction: column;
    width: 25%;
    align-items: center;
    justify-content: center;
  }
</style>