<template>
  <div class="home">
    <b-container>
      <b-row align-v="center">
        <b-col md="12">
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
        </b-col>       
      </b-row>
      </b-container>

      <b-container>
      <b-row align-v="center">
        <b-col md="4">
          <b-card
          img-src="https://picsum.photos/id/137/300/300"
          >
            <b-card-text>Lorem ipsum dolor, sit amet consectetur adipisicing elit.</b-card-text>
          </b-card>
        </b-col>   
         <b-col md="4">
          <b-card
          img-src="https://picsum.photos/id/128/300/300"
          >
            <b-card-text>Lorem ipsum dolor, sit amet consectetur adipisicing elit.</b-card-text>
          </b-card>
        </b-col> 
        <b-col md="4">
          <b-card
          img-src="https://picsum.photos/id/139/300/300"
          >
            <b-card-text>Lorem ipsum dolor, sit amet consectetur adipisicing elit.</b-card-text>
          </b-card>
        </b-col>     
      </b-row>
      </b-container>
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
