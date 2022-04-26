<template>
    <div 
    class="p-3 m-3 w_342 h_513 d-flex text-white" 
    @mouseover="hoverFun(true)" 
    @mouseleave="hoverFun(false)"> 
        <div :class="(hover == true) ? 'd-none' : 'd-block' ">
            <img class="w_342 h_513" :src='`https://image.tmdb.org/t/p/w342${film.poster_path}`' alt="copertina">
        </div>

        <div class="h-100 p-3 overflow_auto" :class="(hover == true) ? 'd-block' : 'd-none' ">
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

            <!-- {{film.vote_average}} -->
            <div v-if="(film.vote_average == 0) && (film.vote_average <= 2)">
                <i class="fa-solid fa-star"></i>
            </div> 
            <div v-else-if="(film.vote_average > 2) && (film.vote_average <= 4)">
                <i class="fa-solid fa-star"></i>
                <i class="fa-solid fa-star"></i>
            </div>
            <div v-else-if="(film.vote_average > 4) && (film.vote_average <= 6)">
                <i class="fa-solid fa-star"></i>
                <i class="fa-solid fa-star"></i>
                <i class="fa-solid fa-star"></i>
            </div>
            <div v-else-if="(film.vote_average > 6) && (film.vote_average <= 8)">
                <i class="fa-solid fa-star"></i>
                <i class="fa-solid fa-star"></i>
                <i class="fa-solid fa-star"></i>
                <i class="fa-solid fa-star"></i>
            </div>
            <div v-else-if="(film.vote_average > 8) && (film.vote_average <= 10)">
                <i class="fa-solid fa-star"></i>
                <i class="fa-solid fa-star"></i>
                <i class="fa-solid fa-star"></i>
                <i class="fa-solid fa-star"></i>
                <i class="fa-solid fa-star"></i>
            </div>
            
            <div>
                <p>
                   {{film.overview}}
                </p> 
            </div>
        </div>
    </div>
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
        }
    }
}
</script>

<style scoped lang="scss">
div {
    i {
        color: yellow;
    }
    h6, span {
        text-transform: capitalize;
    }
}

.lang_img {
    height: 15px;
    width: 20px;
}

.w_342 {
    width: 342px;
}

.h_513 {
    height: 513px;
}

.overflow_auto {
    overflow: auto;
}
</style>