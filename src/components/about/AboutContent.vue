<template>
  <div class="aboutContent">
    <main>
      <div class="main-header">
        <section class="main-header-wrape">
          <div class="transition-box">
            <transition name="carousel-pop-up" appear>
              <h1>ABOUT COMPONENT </h1>
            </transition>
          </div>
          <div class="transition-box">
            <transition name="carousel-pop-up" appear>
            <p>HEADER TITLE</p>
            </transition>
          </div>
          <div class="transition-box">
            <transition name="carousel-pop-up" appear>
            <p>path:/about </p>
            </transition>
          </div>
        </section>
      </div>

      <transition name="mainCon" appear>
        <div  class="main-content">
            <!-- col2-content title  1111111111111111111111111111-->
            <div class="col2-content">
              <div class="col-block left-block">
                <div class="section-block caption-section">
                  <div v-for="(h1LeftArrey, index) in h1LeftArreys " :key="index">
                    <div class="transition-box" >
                      <transition v-bind:name="h1LeftArrey.tName" appear>
                        <div><p v-bind:style="{color: h1LeftArrey.tColor}">{{h1LeftArrey.tText}}</p></div>
                      </transition>
                    </div>
                  </div>
                </div>
              </div>
              <div class="col-block right-block">
                <div class="section-block image-section">
                  <!-- <div v-for="(h1RightArrey, index ) in h1RightArreys " :key="index">
                    <div class="transition-box" >
                      <transition v-bind:name="h1RightArrey.tName" appear>
                        <div><h1 v-bind:style="{color: h1RightArrey.tColor}">{{h1RightArrey.tText}}</h1></div>
                      </transition>
                    </div>
                  </div> -->
                </div>
              </div>
            </div>
<!-- about team aboutaboutaboutaboutaboutaboutaboutabout -->
            <div class="card-content">
              <div class="card-section card-row">
                <div class="card-container col2-block" v-for=" (cardData, index) in cardDatas" v-bind:key="index">
                  
                  <div v-bind:id="cardData.id" class="card-wrap" v-bind:class="{cardMarginTop: !(index % 2 == 0) }" >
                    <transition name="spinX3d">
                      <div class="image-box" v-if="MaxScrollY > cardSectionPosition[index]">
                        <img v-bind:src="cardData.img" >
                      </div>
                    </transition>
                    <div class="subscription-box">
                      <div class="subscription-wrap">
                        <transition name="spinX3d">
                        <div class="title" v-if="MaxScrollY > cardSectionPosition[index]">{{cardData.title}}</div>
                        </transition>
                        <transition name="spinX3d">
                        <div class="subscription" v-if="MaxScrollY > cardSectionPosition[index]">{{cardData.subscription}}</div>
                        </transition>
                      </div>
                    </div>
                  </div>

                </div>
              </div>
            </div>
            
             
              
            

            <!-- image component alternation 1111111111111111111111111111-->
            
            <div class="alternationImage-content alternation-row">
              <div class="col-block text-block">
                <div id="img1Captionblock" class="section-block caption-section">
                 
                  <div class="caption-group caption-group-right" v-if="page==='about'">
                    <div v-for="(img1Arrey, index ) in img1Arreys " :key="index">
                      <div class="transition-box" >
                        <transition v-bind:name="img1Arrey.tName" >
                            <h2 v-if="MaxScrollY > img1Captionblock"
                                v-bind:style="{color: img1Arrey.tColor}"  >
                              {{img1Arrey.tText}}
                            </h2>
                        </transition>
                      </div>
                    </div>
                    <div class="link-group">
                      <div class="link-unit">
                        <transition name="link-lineMotion-works" >
                          <div class="link-nextPage" v-if="MaxScrollY > img1Captionblock">
                              <a v-on:click="link_commit('about', '/about')" >
                                <div class="next-text">
                                    ABOUT
                                </div>
                              </a>
                              <a v-on:click="link_commit('about', '/about')" >
                                <div class="link-arrow" >
                                  <svg width="60" height="60" >
                                    <line x1="0" y1="30" x2="60" y2="30"  />
                                    <polygon  points="56,26 56,34 60,30"/>
                                  </svg>
                                </div>
                              </a>
                              <a v-on:click="link_commit('about', '/about')" >
                                <div class="link-circle" >
                                  <svg width="60" height="60">
                                    <circle cx="30" cy="30" r="24" />
                                  </svg> 
                                </div>
                              </a>
                          </div>
                        </transition>
                      </div>
                    </div>
                  
                  </div>

                </div>
              </div>
              
              <div id="img1Imageblock" class="col-block image-block ">
                 <div class="image-section-block  image-section image-right" >
                  
                  <transition name="box-shadow-moveRight" >
                    <div class="box-shadow box-shadow-right" v-if="MaxScrollY > img1Imageblock">
                      <img v-bind:src="imgURL1" >
                    </div>
                  </transition>
                  <transition name="rippleRight" >
                    <img v-bind:src="imgURL1" v-if="MaxScrollY > img1Imageblock"  alt="img1">
                  </transition>
                  <!-- <transition name="rippleRight" >
                    <div class="image-filter image-filter-right" v-if="MaxScrollY > img1Imageblock">
                      <img v-bind:src="imgURL1">
                    </div>
                  </transition> -->
                </div>
              </div>
              
            </div>

            <!-- col2-content title  222222222222222-->
            <div class="col2-content">
              <div class="col-block left-block">
                <div class="section-block caption-section">

                  <div v-for="(h1LeftArrey, index) in h1LeftArreys " :key="index">
                    <div class="transition-box" >
                      <transition v-bind:name="h1LeftArrey.tName" appear>
                        <div><p v-bind:style="{color: h1LeftArrey.tColor}">{{h1LeftArrey.tText}}</p></div>
                      </transition>
                    </div>
                  </div>
                  <!-- <div class="transiton-box ">
                    <transition name="carousel-pop-up" appear>
                      <p>Alprime Capital AG (“Alprime”) is a Swiss investment boutique focusing on alternative investments. It was approved as an asset manager of collective investment schemes by the Swiss Financial Market Supervisory Authority (FINMA) in summer 2018. Alprime was established in Baar (Canton Zug/Switzerland) as a spin-off from Progressive Capital Partners Ltd in April 2018. Alprime is owned entirely by its co-founders who also manage the company.</p>
                    </transition>
                  </div>-->
                </div>
              </div>
              <div class="col-block right-block">
                <div class="section-block image-section">

                  <div v-for="(h1RightArrey, index ) in h1RightArreys " :key="index">
                    <div class="transition-box" >
                      <transition v-bind:name="h1RightArrey.tName" appear>
                        <div><h1 v-bind:style="{color: h1RightArrey.tColor}">{{h1RightArrey.tText}}</h1></div>
                      </transition>
                    </div>
                  </div>
                  
                </div>
              </div>
            </div>

            <!-- image component alternation 222222222222222222222222222222222-->
            <div class="alternationImage-content alternation-revers">
              <div id="img2Captionblock" class="col-block text-block">
                <div  class="section-block caption-section ">
                  <div class="caption-group caption-group-left">
                    <div  v-for="(img2Arrey, index ) in img2Arreys " :key="index">
                      <div class="transition-box" >
                        <transition v-bind:name="img2Arrey.tName" >
                            <h2 v-if="MaxScrollY > img2Captionblock" 
                              v-bind:style="{color: img2Arrey.tColor}">
                              {{img2Arrey.tText}}
                            </h2>
                        </transition>
                      </div>
                    </div>
                    <div class="link-group">
                      <div class="link-unit">
                        <transition name="link-lineMotion-works" >
                          <div class="link-nextPage" v-if="MaxScrollY > img2Captionblock">
                              <a v-on:click="link_commit('contact', '/contact')" >
                                <div class="next-text">
                                    Contact
                                </div>
                              </a>
                              <a v-on:click="link_commit('contact', '/contact')" >
                                <div class="link-arrow" >
                                  <svg width="60" height="60" >
                                    <line x1="0" y1="30" x2="60" y2="30"  />
                                    <polygon  points="56,26 56,34 60,30"/>
                                  </svg>
                                </div>
                              </a>
                              <a v-on:click="link_commit('contact', '/contact')" >
                                <div class="link-circle" >
                                  <svg width="60" height="60">
                                    <circle cx="30" cy="30" r="24" />
                                  </svg> 
                                </div>
                              </a>
                          </div>
                        </transition>
                      </div>
                    </div>
                  </div>
                </div>
              </div>
              <div id="img2Imageblock" class="col-block image-block ">
                 <div class="image-section-block  image-section image-left">

                  <!-- <transition name="rippleLeft" >
                    <img v-bind:src="imgURL2" v-if="MaxScrollY > img2Imageblock"  alt="img2">
                  </transition> -->

                  <transition name="box-shadow-moveLeft" >
                    <div class="box-shadow box-shadow-left" v-if="MaxScrollY > img2Imageblock">
                      <img v-bind:src="imgURL2" >
                    </div>
                  </transition>
                  <transition name="rippleLeft" >
                    <img v-bind:src="imgURL2" v-if="MaxScrollY > img2Imageblock"  alt="img2">
                  </transition>
                  <!-- <transition name="rippleLeft" >
                    <div class="image-filter image-filter-left" v-if="scrollY > img2Imageblock">
                      <img v-bind:src="imgURL2">
                    </div>
                  </transition> -->
                </div>
              </div>
            </div>

        </div>
      </transition>
      <FooterBar  msg="footerBar"
                  navMenu="prpject"
                  v-bind:footerTop= "true"
                  v-bind:footerBottom= "true"
                  v-bind:footerMenu= "true"
                  v-bind:footerSepalater= "true"
                  />
    </main>
  </div>
</template>

<script>
import FooterBar from '@/components/footer/FooterBar.vue'

export default {
  name: 'AboutContent',
  props: {
    msg: String,
  },
  components: {
    FooterBar,
  },
  data () {
    return {
      imgURL1: require("../../assets/img/img1578.jpg"),
      imgURL2: require("../../assets/img/fuji1.jpg"),
      imgURL3: require("../../assets/img/img4130b.jpg"),
      imgURL4: require("../../assets/img/img3668.jpg"),
      logoSvgHWorksWhite: require("../../assets/logo/h-works1200x600white.svg"),
      logoSvgHWorksBlack: require("../../assets/logo/h-works1200x600black.svg"),

      scrollY: 0,
      MaxScrollY: 0,
      innerHeight: 0, 

      menuVisible: String,
      mobileBarType: String,
      mobileBarAction: String,
      cardDatas:[
        {id:"card0",img: require("../../assets/img/img1578.jpg"), title: "title1", subscription: "subscription1"  },
        {id:"card1",img: require("../../assets/img/fuji1.jpg"), title: "title2", subscription: "subscription2"  },
        {id:"card2",img: require("../../assets/img/img4130b.jpg"), title: "title3", subscription: "subscription3"  },
        {id:"card3",img: require("../../assets/img/img3668.jpg"), title: "title4", subscription: "subscription4"  },
      ],
      cardSectionPosition:[],
      h1LeftArreys:[
        {tName: "carousel-pop-up1", 
          tText: "Alprime Capital AG (“Alprime”) is a Swiss investment boutique focusing on alternative investments. It was approved as an asset manager of collective investment schemes by the Swiss Financial Market Supervisory Authority (FINMA) in summer 2018. Alprime was established in Baar (Canton Zug/Switzerland) as a spin-off from Progressive Capital Partners Ltd in April 2018. Alprime is owned entirely by its co-founders who also manage the company."
          , tColor:"rgba(0,0,0,.6)" },
        {tName: "carousel-pop-up2",  tText:
          "At Alprime our aim is to provide uncorrelated investment products with stable asset growth. We are convinced that our product offering provides a valuable addition to every portfolio."
          , tColor:"rgba(0,0,0,.6)"},
        {tName: "carousel-pop-up3",  tText:
          "It is our ambition to accept the challenges of changing market environments. We are constantly striving to find new and innovative ways to put our funds to work and to differentiate ourselves from other market players in order to achieve better results for our clients. Our risk management is essential in everything we do since the trust of our clients is the most important asset we have."
          , tColor:"rgba(0,0,0,.6)"},
      ],
      h1RightArreys:[
        {tName: "carousel-pop-up1",  tText: "At Alprime our mission", tColor:"rgba(0,0,0,.6)" },
        {tName: "carousel-pop-up2",  tText: "is offering true alternatives", tColor:"rgba(0,0,40,1)" },
        {tName: "carousel-pop-up3",  tText: "to traditional investments", tColor:"rgba(0,0,40,1)" },
        {tName: "carousel-pop-up4",  tText: "by thinking outside the box.", tColor:"rgba(0,0,0,.6)" },
      ],

      img1Arreys:[
        {tName: "text-pop-up1",  tText: "Opportunities. Chances.", tColor:"rgba(0,0,0,.6)"},
        {tName: "text-pop-up2",  tText: "Our mission: Prime", tColor:"rgba(0,0,40,1)"},
        {tName: "text-pop-up3",  tText: "products and services.", tColor:"rgba(0,0,40,1)"},
        {tName: "text-pop-up4",  tText: "Focusing on your needs.", tColor:"rgba(0,0,0,.6)"},
      ],
      img1Captionblock: 0,
      img1Imageblock: 0,

      img2Arreys:[
        {tName: "text-pop-up1",  tText: "Expertise. Spirit.", tColor:"rgba(0,0,0,.6)"},
        {tName: "text-pop-up2",  tText: "Prime experience and", tColor:"rgba(0,0,40,1)" },
        {tName: "text-pop-up3",  tText: "dedication. Focusing on", tColor:"rgba(0,0,40,1)" },
        {tName: "text-pop-up4",  tText: "risk and performance.", tColor:"rgba(0,0,0,.6)" },
      ],
      img2Captionblock: 0,
      img2Imageblock: 0,
    }
  },
  computed: {
    page () {
    return this.$store.state.page
    },
  },
  mounted: function () {
    window.addEventListener('scroll', this.handleScroll);
    this.init();
  },
  destroyed: function () {
    window.removeEventListener('scroll', this.handleScroll);
  },
  methods: {
    handleScroll() {
      for (var i = 0; i < this.cardDatas.length; i++) {
       
        this.cardSectionPosition[i] = document.getElementById(this.cardDatas[i].id).getBoundingClientRect().top
                          + window.scrollY  - (window.innerHeight*0.7) ;
      }
      this.img1Captionblock = document.getElementById('img1Captionblock').getBoundingClientRect().top
                          + window.scrollY  - (window.innerHeight*0.8) ;
      this.img1Imageblock = document.getElementById('img1Imageblock').getBoundingClientRect().top
                          + window.scrollY  - (window.innerHeight*0.8)  ;
      this.img2Captionblock = document.getElementById('img2Captionblock').getBoundingClientRect().top
                          + window.scrollY  - (window.innerHeight*0.8) ;
      this.img2Imageblock = document.getElementById('img2Imageblock').getBoundingClientRect().top
                          + window.scrollY  - (window.innerHeight*0.8)  ;
      this.innerHeight = window.innerHeight;
      this.scrollY = window.scrollY;
      if(this.scrollY > this.MaxScrollY) {
        this.MaxScrollY = this.scrollY;
      }
    },
    init(){
      this.$store.commit( 'about' );
      this.innerHeight = window.innerHeight;
      this.scrollY = window.scrollY;
    },
    link_commit(link, link_path) {
      this.$store.commit( link );
      setTimeout( () => {
        this.$router.push({ path: link_path });
      }, 500);
    },
  },
}
</script>

<style scoped lang="scss">
@import "../../assets/scss/common/data/thema.scss";
.aboutContent{
    position: relative;
    width: 100%;
    height: auto;
    padding-top: $header-height;
}
main{
  margin: 0;
  padding: 0;
}
.main-header{
  height: 35vh;
  padding: 1rem 1rem;
  //横スクロール処理
  // width: auto;
  // min-width: 100vw;
  width: 100vw;
}
.main-header-wrape{
  position: relative;
  width: 100%;
  height: 100%;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: flex-start;
  padding: 2rem;
}
.transition-box{
  width: 100%;
  overflow: hidden;
  margin-bottom: 0.5rem;
}
.main-header h1,  .main-header p{
  color: $header-text;
}
.main-header h1{
  font-size: 3rem;
  @media (min-width: 992px){
    font-size: 4rem;
  }
}

.main-content{
  // height: 75vh;
  height:100%;
  background-color: $main-contents-color;
  color: $main-contents-text;
  //横スクロール処理
  // width: auto;
  // min-width: 100vw;
  width: 100vw;
} 

//section-2col
.col2-content{
  position: relative;
  width: 100%;
  height: 100%;
  display:flex;
  flex-wrap: wrap;
}

.col-block{
  width: 100%;
  @media (min-width: 992px){
    width: 50%;
  }
}

.left-block{
  // background-color: rgba(0,0,0,.1);
  // border:  1px solid red;
 
}
.right-block{
  // background-color: rgba(0,0,0,.3);
  // border:  1px solid green;
}

.section-block{
  position: relative;
  width:100;
  height:100%;
  padding: 1.6rem;
  @media (min-width: 992px){
    padding: 6rem 0 6rem 6rem ;
  } 
  @media (min-width: 1200px){
    padding: 6rem 0 6rem 12rem ;
  } 
}
.image-section-block{
  position: relative;
  @media (min-width: 992px){
    padding: 12rem 0;
  } 
}

.caption-section{
  // border:  1px dotted red;
}
.image-section{
  // border:  1px dotted yellow;
}

.caption-group{
  position: relative;
  width: 100%;
  @media (min-width: 992px){
    position: absolute;
    top: 50%;
    left: 50%;
    z-index: 1;
    transform: translateY(-50%);
  } 
}
.caption-group p, .caption-group h1, .caption-group h2{
  color: rgba(0, 0, 0, 1);
  text-shadow: 1px 1px 0px #fff,
               2px 2px 0px rgba(0,0,0,0.2),
               3px 3px 0px rgba(0,0,0,0.15);
}
.caption-group-right{
  left: 0%;
  padding-left: 0;
  text-align:left;
  @media (min-width: 992px){
    text-align:left;
    left: 50%;
    padding-left: 0%;
  }
}
.caption-group-left{
  left: 0%;
  padding-left: 0;
  text-align:right;
  @media (min-width: 992px){
    text-align:left;
    left: -8%;
    padding-left: 0%;
  }
}
.link-group{
  position:relative;
  width: 100%;
  height: 60px;
}

// alternation-------------------------
.alternationImage-content{
  position: relative;
  width: 100%;
  height: 100%;
  display:flex;
  flex-wrap: wrap;
  flex-direction: row;
}
.alternation-row{
  flex-direction: row;
}
.alternation-revers{
  flex-direction: row-reverse;
}
// alternation virtical#####################
.card-content{
  position:relative;
  width:100%;
  height:100%;
}
.card-section{
  position: relative;
  width: 100%;
  height: 100%;
  display:flex;
  flex-wrap: wrap;
}
.card-row{
  flex-direction: row;
}

.col2-block{
  width: 100%;
  @media (min-width: 992px){
    width: 50%;
  }
}
.card-container{
  padding: 1rem 1rem;
  @media (min-width: 992px){
    padding: 5rem 10rem;
  }
}
.card-wrap{
  // border: 1px dotted red;
}
.cardMarginTop{
  margin-top: 0rem;
  @media (min-width: 992px){
    margin-top: 10rem;
  }
  
}

.image-box img{
  width: 100%;
  height: auto;
  
}
.subscription-wrap{
  padding: 1rem;
}


.text-block{
  width: 100%;
  @media (min-width: 992px){
    width: 30%;
  }
 
}
.image-block{
  width: 100%;
  @media (min-width: 992px){
    width: 70%;
  }
}
.image-block .image-section{
  // overflow:hidden;
}

.image-block .image-section img{
  width: 100%;
  height: auto;
}
.image-block .image-right img{
  clip-path: circle(150% at 0 100%);
}
.image-block .image-left img{
  clip-path: circle(150% at 100% 100%);
}
.box-shadow{
  position: absolute;
  top:0;
  left: 0;
  background-color: rgba(0,0,255,.1);
  width: 100%;
  height: auto;
  transform: translate(-100px, 100px);
  img{
    opacity:0;
  }
  display: none;
  @media (min-width: 992px){
    display: block;
    margin-top: 10rem;
  }
}
.box-shadow-right{
  transform: translate(-100px, 100px);
}
.box-shadow-left{
  transform: translate(100px, 100px);
}
.image-filter{
  position: absolute;
  z-index: 1;
  top:0;
  left: 0;
  background-color: rgba(0,250,250,.2);//blue
  width: 100%;
  height: auto;
  img{
    opacity:0;
  }
  display:none;
  @media (min-width: 992px){
    display: block;
    margin-top: 12rem;
  }
  
}
.image-filter-right{
  clip-path: circle(150% at 0% 100%) ;
}
.image-filter-left{
  clip-path: circle(150% at 100% 100%) ;
}

// link-unit--------------------
.link-unit{
  position:relative;
  width: 100%;
}
.caption-group-right .link-nextPage{
  position: absolute;
  top: 0;
  left: -55px;
  z-index:10;
}
.caption-group-left .link-nextPage{
  position: absolute;
  top: 0;
  left: 90px;
  z-index:10;
}
.link-nextPage{
  
  cursor: pointer;
  width: 200px;
  height: 60px;
  display: flex;
  justify-content: flex-start;
  align-items: center;
  padding: 0 1rem ;
  &:hover{
    animation: link-hoverActionSlide .25s  forwards cubic-bezier(0.320, 0.625, 0.580, 1.000);//sharp;;
    .link-circle svg {
      animation: link-hoverAction .5s   forwards cubic-bezier(0.320, 0.625, 0.580, 1.000);//sharp;;
    }
  }
}
.link-nextPage a .next-text{
  // border: 1px solid red;
   width:100px;
   margin-right: 0.4rem;
   text-transform: uppercase;
   text-align: right;
   color: rgba(0,0,40,1);
}
.link-nextPage a .link-arrow svg {
  line {
    fill: rgba(0,0,0,1);
    stroke: rgba(0,0,0,1);
    stroke-width: 1;
  }
  polygon {
    fill: rgba(0,0,0,1);
    stroke: rgba(0,0,0,1);
    stroke-width: 1;
  }
}
.link-nextPage a .link-circle{
  opacity: 1;
  cursor: pointer;
  margin-left: -32px;
}
.link-circle svg {
  transform: rotate(-90deg);
  circle {
    fill: transparent;
    stroke: rgba(0,0,0,1);
    stroke-width: 1;
  }
}
@keyframes link-hoverActionSlide {
  0% {  transform: translateX(0); }
  100% { transform: translateX(25px);}
}
@keyframes link-hoverAction {
  0% { opacity: 1; transform: scale(1); }
  45% { opacity: 0; transform: scale(1.2);}
  50% { opacity: 0; transform: scale(.6);}
  100% { opacity: 1; transform: scale(1);}
}


</style>
