<template>
    <div class="flip-card">
        <div class="flip-card-inner col text-white w-100">
            <div 
            class="flip-card-front card_bg"
            :style="{ backgroundImage: `url(https://image.tmdb.org/t/p/w342${serie.poster_path})` }">
            </div>

            <div class="flip-card-back overflow_auto p-2">
                
                <div>
                    <h4>
                        {{serie.name}}
                    </h4> 
                </div>
                <div class="py-2">
                    <h6>
                        original title: {{serie.original_name}}
                    </h6>
                </div>
                <div v-if='serie.original_language == "en" '>
                    <span>original language </span>
                    <img src="../../assets/img/Flag_of_the_United_Kingdom.svg" alt="en" class="lang_img">
                </div>
                <div v-else-if='serie.original_language == "it" '>
                    <span>original language </span>
                    <img src="../../assets/img/Flag_of_Italy.svg" alt="it" class="lang_img">
                </div>
                <div v-else-if='serie.original_language == "ja" '>
                    <span>original language </span>
                    <img src="../../assets/img/Flag_of_Japan.svg" alt="jp" class="lang_img">
                </div>
                <div v-else>
                    <span>original language </span>
                    {{serie.original_language}}
                </div>

                <div>
                    <p>
                       {{serie.vote_average}}
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
                       {{serie.overview}}
                    </p> 
                </div>
                
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'SerieSub',
    props: {
        serie: Object,
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
            const star = Math.ceil(this.serie.vote_average) / 2
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
  aspect-ratio: 0.8;
  perspective: 1000px;
}

.flip-card-inner {
  position: relative;
  width: 100%;
  height: 100%;
  transition: transform 0.8s;
  transform-style: preserve-3d;
}

.flip-card:hover .flip-card-inner {
  transform: rotateY(180deg);
}

.flip-card-front, .flip-card-back {
  position: absolute;
  width: 100%;
  height: 100%;
  -webkit-backface-visibility: hidden;
  backface-visibility: hidden;
}

.flip-card-front {
  background-color: #bbb;
  color: black;
}

.flip-card-back {
  color: white;
  transform: rotateY(180deg);
}
</style>