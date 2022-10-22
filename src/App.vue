<template>
  <div class="app" style="margin-top: 40px;">
      <carousel >
          <carousel-slide v-for="slide in slides" :key="slide" class="carousel-slider">
              <img :src="slide" :alt="slide">
          </carousel-slide>
      </carousel>
  </div>    
</template>

<script>
import Carousel from './components/carousel/Carousel.vue';
import CarouselSlide from './components/carousel/CarouselSlide';

export default {
  data(){
      return {
          slides: [
              'https://picsum.photos/seed/picsum/200/300',
              'https://picsum.photos/id/231/600/300',
              'https://picsum.photos/id/232/600/300',
              'https://picsum.photos/id/237/200/300',
              'https://picsum.photos/id/238/200/300',
              'https://picsum.photos/id/235/600/300',
              'https://picsum.photos/200/300?grayscale',
          ]
      }
  },

  components : {
      Carousel : Carousel,
      CarouselSlide : CarouselSlide,
  }
}
</script>

<style>
@import 'https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.2.0/css/all.min.css';
  .app {
      display:flex;
      justify-content: center;
  }
  .carousel {
      position:relative;
      overflow: hidden;
      width:800px;
      height:400px;
      z-index:10;
  }
  .btn {
      padding:5px 10px;
      background-color:rgba(0,0,0,0.5);
      border:1px solid transparent;
      margin:5px 10px;
      color:#FFF;
      height:50px;
      width:50px;
      position:absolute;
      margin-top:-25px;
      z-index:2;
  }
  .btn:hover {
      cursor: pointer;
  }
  .btn:focus{
      outline:none;
  }
  .btn-next {
      top:50%;
      right:0;
  }
  .btn-prev {
      top:50%;
      left:0;
  }
  .carousel-slider {
      position:absolute;
      top:0;
      left:0;
      bottom:0;
      right:0;
  }
  .carousel-slider img {
      width:100%;
      height:100%;
  }

</style>