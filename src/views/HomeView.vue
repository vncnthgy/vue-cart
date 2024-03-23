<template>
  <div class="home">
    <h1>New Arrival</h1>
    <div class="column">
      <img v-for="(src, index) in images" :src="src" :key="index" v-show="currentImage === index" width="400" height="400"/>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      currentImage: 0,
      images: [
        '/images/rtx1.png',
        '/images/rtx2.png',
        '/images/rtx3.png',
        '/images/rtx4.png',
        '/images/rtx5.png',
        '/images/rtx6.png',
        '/images/rtx7.png',
        '/images/rtx8.png'
      ]
    }
  },
  created() {
    setInterval(() => {
      this.currentImage = (this.currentImage + 1) % this.images.length;
    }, 2000);
  }
}
</script>