<template>
  <div class="carouselFullScreenBasic">
    <div class="carousel-wrapper">
      <div id="vue-carousel" class="vue-carousel ">
          <!-- nav -->
          <div class="fixed-layer">
            <div class="nav-position">
              <span v-on:click="back_page()">prev</span>
            </div>
            <div class="nav-position" >
              <span v-on:click="next_page()">next</span>
            </div>
          </div>
          <!-- slider -->
          <transition-group  v-bind:name="transition_name" >
            <div class="vue-carousel_body" :key="index"
                v-for="(content, index) in contents"
                v-if="visible_content == index">
                <!-- fullscreen-img -->
                <div class="full-img-wrap"
                    v-bind:style="{ 'background-image' : 'url(' + contents[index].imgURL + ')' }"
                    
                >
                  <!-- <img v-bind:src="contents[index].imgURL" alt="slide image" id="section1"> -->
                </div>
                 <!-- <div class="full-img-Wrap">
                  <img v-bind:src="contents[index].imgURL" alt="slide image" id="section1">
                </div> -->

            </div>
          </transition-group>
      </div>
    </div>
</div>
</template>

<script>
 export default {
  name: 'CarouselFullScreenBasic',
  props: {
    msg: String
  },
   data () {
      return {
        contents: [{
              title: 'img1',
              bg_color: '#7bbff9',
              imgURL: require("../../assets/img/img1578.jpg"),
            },{
              title: 'img2',
              bg_color: '#f16972',
              imgURL: require("../../assets/img/fuji1.jpg"),
            },{
              title: 'img3',
              bg_color: '#f16972',
              imgURL: require("../../assets/img/img4130b.jpg"),
            },{
              title: 'img4',
              bg_color: '#20d2d3',
              imgURL: require("../../assets/img/img3668.jpg"),
            }],
        transition_name: 'show-next',
        visible_content: 0,
        contents_number: null,
      }
  },
  mounted: function() {
    this.contents_number = this.contents.length;
    this.autoSlide();
  },
  methods: {
    back_page() {
      this.transition_name = 'show-prev';
      this.transition_text = 'show-prev-text';
      if((this.visible_content - 1) === -1) {
        this.visible_content = (this.contents_number - 1);
      }else{
        this.visible_content--;
      }
    },
    next_page() {
      this.transition_name = 'show-next';
      this.transition_text = 'show-next-text';
      this.visible_content =  (this.visible_content + 1) % this.contents_number;
    },
    autoSlide(){
      
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
@import "../../assets/scss/common/data/thema.scss";
.carouselFullScreenBasic{
  position: absolute;
  width: 100%;
  height: 100%;
  margin-top: calc( #{ $header-height } * -1 );
}
.carousel-wrapper{
  position:relative;
  width: 100vw;
  height: 100vh;
  background-color: rgba(0,0,0, .5);
}
.vue-carousel {
  position: absolute;
  width: 100%;
  height: 100%;
  overflow: hidden;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: row;
  &_body {
    position: absolute;
    top: 0;
    left: 0;
    height: 100%;
    width: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
   }
}
.img-wrap{
  width: 50%;
  height:  auto;
}
.full-img-wrap{
  width: 100vw;
  height: 100vh;
  background-repeat: no-repeat;
  background-size: cover;
  background-position: center;
  
}
img{
  width: 100%;
  height: auto;
  display:block;
}
.bg_filter{
      background-color: rgba(0,0,0,.6);
      position: fixed;
      top: 0;
      left: 0;
      min-width: 100%;
      min-height: 100%;
      width: auto;
      height: auto;
      //横スクロール処理
      min-width: 100vw;
  }
.fixed-layer{
  position:fixed;
  display: flex;
  justify-content: space-between;
  align-items: center;
  flex-direction: row;
  z-index: 10;
  width: 100%;
  height: 100%;
}
.fixed-layer{
  .nav-position{
    transform: rotate(-90deg);
    width:12rem;
    border: 1px solid gray;
    text-align:center;
    cursor: pointer;
  }
}

</style>
