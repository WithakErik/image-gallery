<template>
  <div id="container-thumb">
    <ul>
      <li
        v-for="image in images"
        :key="image.id"
      >
        <a @click.prevent="handleZoom(image.id)">
          <div>
            <p>{{ image.title }}</p>
            <img
              :src="image.url"
              :alt="image.title"
            >
          </div>
        </a>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  props: {
    images: Array,
    handleZoom: {
      type: Function,
      required: true
    }
  }
};
</script>

<style scoped>
a, a:hover, a:focus {
  border: none;
  padding: none;
  margin: none;
  background: none;
  padding: 0;
  margin: 0;
}
span {
  display: flex;
  justify-content: space-between;
  flex-wrap: wrap;
  list-style: none;
}
ul {
  padding: 0 13px;
}
li {
  display: inline-block;
  margin: 3px;
  padding: 6px;
  border-top: 3px solid gray;
  border-right: 3px solid black;
  border-bottom: 3px solid black;
  border-left: 3px solid gray;
}
img {
  height: 100px;
  width: auto;
}
</style>
