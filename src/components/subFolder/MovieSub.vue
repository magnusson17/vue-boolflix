<template>
    <div class="flip-card">
        <div class="flip-card-inner col text-white w-100">
            <div 
            class="flip-card-front card_bg"
            :style="{ backgroundImage: `url(https://image.tmdb.org/t/p/w342${film.poster_path})` }">
            </div>

            <div class="flip-card-back overflow_auto p-2">
                
                <div>
                    <h4>
                        {{film.title}}
                    </h4> 
                </div>
                <div class="py-2">
                    <h6>
                        original title: {{film.original_title}}
                    </h6>
                </div>
                <div v-if='film.original_language == "en" '>
                    <span>original language </span>
                    <img src="../../assets/img/Flag_of_the_United_Kingdom.svg" alt="en" class="lang_img">
                </div>
                <div v-else-if='film.original_language == "it" '>
                    <span>original language </span>
                    <img src="../../assets/img/Flag_of_Italy.svg" alt="it" class="lang_img">
                </div>
                <div v-else-if='film.original_language == "ja" '>
                    <span>original language </span>
                    <img src="../../assets/img/Flag_of_Japan.svg" alt="jp" class="lang_img">
                </div>
                <div v-else>
                    <span>original language </span>
                    {{film.original_language}}
                </div>

                <div>
                    <p>
                       {{film.vote_average}}
                       <i 
                       class="fa-star" 
                       v-for="i in 5" 
                       :key="i" 
                       :class="(i <= starsFun() ? 'fa-solid' : 'fa-regular')">
                       </i> 
                    </p>
                </div>
            
                <div>
                    <p>
                       {{film.overview}}
                    </p> 
                </div>
                
            </div>
        </div>
    </div>
    <!-- <div
    @mouseover="hoverFun(true)"
    @mouseleave="hoverFun(false)"   
    class="row row-cols-4 g-3 text-white">
        <div class="col">
            
            <div
            :class="(hover == true) ? 'd-none' : 'd-block' ">
                <img class="img-fluid" :src='`https://image.tmdb.org/t/p/w342${film.poster_path}`' alt="copertina">
            </div>
            

            <div  class="h-100 p-3 overflow_auto" :class="(hover == true) ? 'd-block' : 'd-none' ">
                <div>
                    <h4>
                        {{film.title}}
                    </h4> 
                </div>
                <div class="py-2">
                    <h6>
                        original title: {{film.original_title}}
                    </h6>
                </div>
                <div v-if='film.original_language == "en" '>
                    <span>original language </span>
                    <img src="../../assets/img/Flag_of_the_United_Kingdom.svg" alt="en" class="lang_img">
                </div>
                <div v-else-if='film.original_language == "it" '>
                    <span>original language </span>
                    <img src="../../assets/img/Flag_of_Italy.svg" alt="it" class="lang_img">
                </div>
                <div v-else-if='film.original_language == "ja" '>
                    <span>original language </span>
                    <img src="../../assets/img/Flag_of_Japan.svg" alt="jp" class="lang_img">
                </div>
                <div v-else>
                    <span>original language </span>
                    {{film.original_language}}
                </div>

                <div>
                    <p>
                       {{film.vote_average}}
                       <i 
                       class="fa-star" 
                       v-for="i in 5" 
                       :key="i" 
                       :class="(i <= starsFun() ? 'fa-solid' : 'fa-regular')">
                       </i> 
                    </p>
                </div>
            
                <div>
                    <p>
                       {{film.overview}}
                    </p> 
                </div>

            </div>
        </div>
    </div> -->
</template>

<script>
export default {
    name: 'MovieSub',
    props: {
        film: Object,
    },
    
    data() {
        return {
            hover: false,
        }
    },

    methods: {
        hoverFun(h) {
            this.hover = h;
        },

        starsFun() {
            const star = Math.ceil(this.film.vote_average) / 2
            return star
        }
    }
}
</script>

<style scoped lang="scss">
@import '../mixin.scss';

.card_bg {
    @include backgroundBasic(no-repeat, cover, center);
}

div {
    h6, span {
        text-transform: capitalize;
    }
}

.lang_img {
    height: 15px;
    width: 20px;
}

.overflow_auto {
    overflow: auto;
}

/* The flip card container - set the width and height to whatever you want. We have added the border property to demonstrate that the flip itself goes out of the box on hover (remove perspective if you don't want the 3D effect */
.flip-card {
  background-color: transparent;
  // width: 100%;
  // height: 400px;
  aspect-ratio: 0.8;
  // border: 1px solid #f1f1f1;
  perspective: 1000px; /* Remove this if you don't want the 3D effect */
}

/* This container is needed to position the front and back side */
.flip-card-inner {
  position: relative;
  width: 100%;
  height: 100%;
  // text-align: center;
  transition: transform 0.8s;
  transform-style: preserve-3d;
}

/* Do an horizontal flip when you move the mouse over the flip box container */
.flip-card:hover .flip-card-inner {
  transform: rotateY(180deg);
}

/* Position the front and back side */
.flip-card-front, .flip-card-back {
  position: absolute;
  width: 100%;
  height: 100%;
  -webkit-backface-visibility: hidden; /* Safari */
  backface-visibility: hidden;
}

/* Style the front side (fallback if image is missing) */
.flip-card-front {
  background-color: #bbb;
  color: black;
}

/* Style the back side */
.flip-card-back {
  // background-color: black;
  color: white;
  transform: rotateY(180deg);
}
</style>