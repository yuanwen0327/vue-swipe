<template>
  <div>
    <h1>Default</h1>
    <swipe class="my-swipe">
      <swipe-item class="slide1">Slide1</swipe-item>
      <swipe-item class="slide2">Slide2</swipe-item>
      <swipe-item class="slide3">Slide3</swipe-item>
    </swipe>
  
    <br>

    <h1>Change swipe</h1>
    <swipe class="my-swipe" ref="mySwipe2" :auto="0" :continuous="false" :show-indicators="false" @change="changeSwipe">
      <swipe-item class="slide1">Slide1</swipe-item>
      <swipe-item class="slide2">Slide2</swipe-item>
      <swipe-item class="slide3">Slide3</swipe-item>
    </swipe>

    <button @click="goto(2)">goto page 3</button>
    <button @click="goto(0)">goto page 1</button>
  
    <br>

    <h1>Drag single swipe</h1>
    <swipe class="my-swipe" :speed="900" :auto="0" :show-indicators="false" :no-drag-when-single="false">
      <swipe-item class="slide1">SINGLE SLIDE</swipe-item>
    </swipe>

    <br>

    <h1>Default index</h1>
    <swipe class="my-swipe" :defaultIndex="1" :auto="0">
      <swipe-item class="slide1">Slide1</swipe-item>
      <swipe-item class="slide2">Slide2</swipe-item>
      <swipe-item class="slide3">Slide3</swipe-item>
    </swipe>

    <br>

    <h1>Lazy image</h1>
    <swipe class="my-swipe">
      <swipe-item class="slide1"><img data-src="./images/nature1.jpg"></swipe-item>
      <swipe-item class="slide2"><img data-src="./images/nature2.jpg"></swipe-item>
      <swipe-item class="slide3"><img data-src="./images/nature3.jpg"></swipe-item>
    </swipe>
  </div>
</template>

<script>
  import { Swipe, SwipeItem } from '../src';

  export default {
    components: {
      swipe: Swipe,
      swipeItem: SwipeItem
    },

    methods: {
      goto(index) {
        this.$refs.mySwipe2.goto(index);
      },
      changeSwipe(newIndex, oldIndex) {
        console.log(`swipe from ${oldIndex} to ${newIndex}`);
      }
    }
  };
</script>

<style scoped>
  .my-swipe {
    height: 200px;
    color: #fff;
    font-size: 30px;
    text-align: center;
  }
  .my-swipe img{
    display: block;
    width: 100%;
    height: 100%;
  }
  .slide1 {
    background-color: #0089dc;
    color: #fff;
  }
  .slide2 {
    background-color: #ffd705;
    color: #000;
  }
  .slide3 {
    background-color: #ff2d4b;
    color: #fff;
  }
</style>
