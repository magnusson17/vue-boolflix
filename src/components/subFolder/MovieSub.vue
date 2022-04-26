<template>
    <div 
    class="p-3" 
    @mouseover="hoverFun(true)" 
    @mouseleave="hoverFun(false)"> 
        <div :class="(hover == true) ? 'd-none' : 'd-block' ">
            <img :src='`https://image.tmdb.org/t/p/w500${film.backdrop_path}`' alt="copertina">
        </div>

        <div :class="(hover == true) ? 'd-block' : 'd-none' ">
            <div>{{film.title}}</div>
            <div>{{film.original_title}}</div>
            <div v-if='film.original_language == "en" '>
                <img src="../../assets/img/Flag_of_the_United_Kingdom.svg" alt="en" class="lang_img">
            </div>
            <div v-else-if='film.original_language == "it" '>
                <img src="../../assets/img/Flag_of_Italy.svg" alt="it" class="lang_img">
            </div>
            <div v-else-if='film.original_language == "ja" '>
                <img src="../../assets/img/Flag_of_Japan.svg" alt="jp" class="lang_img">
            </div>
            <div v-else>
                {{film.original_language}}
            </div>

            <div v-if="(film.vote_average == 0) && (film.vote_average <= 2)">
                {{film.vote_average}}
                <i class="fa-solid fa-star"></i>
            </div> 
            <div v-else-if="(film.vote_average > 2) && (film.vote_average <= 4)">
                {{film.vote_average}}
                <i class="fa-solid fa-star"></i>
                <i class="fa-solid fa-star"></i>
            </div>
            <div v-else-if="(film.vote_average > 4) && (film.vote_average <= 6)">
                {{film.vote_average}}
                <i class="fa-solid fa-star"></i>
                <i class="fa-solid fa-star"></i>
                <i class="fa-solid fa-star"></i>
            </div>
            <div v-else-if="(film.vote_average > 6) && (film.vote_average <= 8)">
                {{film.vote_average}}
                <i class="fa-solid fa-star"></i>
                <i class="fa-solid fa-star"></i>
                <i class="fa-solid fa-star"></i>
                <i class="fa-solid fa-star"></i>
            </div>
            <div v-else-if="(film.vote_average > 8) && (film.vote_average <= 10)">
                {{film.vote_average}}
                <i class="fa-solid fa-star"></i>
                <i class="fa-solid fa-star"></i>
                <i class="fa-solid fa-star"></i>
                <i class="fa-solid fa-star"></i>
                <i class="fa-solid fa-star"></i>
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
            hover: true,
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
.lang_img {
    height: 10px;
    width: 18px;
}
</style>