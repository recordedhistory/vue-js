<template>
  <div class="home">
    <carousel
      @next="next"
      @prev="prev"
      >
      <carousel-slide v-for="(slide,index) in slides" 
      :key="slide" 
      :index="index"
      :visibleSlide="visibleSlide"
      >
        <img :src="slide" />
      </carousel-slide>
    </carousel>
  </div>
</template>

<script>
// @ is an alias to /src
import Carousel from '@/components/Carousel.vue'
import CarouselSlide from '@/components/CarouselSlide.vue'

export default {
  data() {
    return {
      slides: [
        'https://picsum.photos/id/237/600/300',
        'https://picsum.photos/id/236/600/300',
        'https://picsum.photos/id/235/600/300',
      ],
      visibleSlide : 0,
    }
  },
  computed: {
    slidesLen() {
      return this.slides.length;
    }
  },
  methods: {
    next() {
      if(this.visibleSlide >= this.slidesLen - 1) {
        this.visibleSlide = 0;
      }
      else {
        this.visibleSlide++;
      }
    },
    prev() {
      if(this.visibleSlide <= 0) {
              this.visibleSlide = this.slidesLen - 1;
            }
            else {
              this.visibleSlide--;
            }
    }
  },
  name: 'Home',
  components: {
    Carousel,
    CarouselSlide,
  }
}
</script>
