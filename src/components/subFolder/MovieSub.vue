<template>
    <div class="p-3"> 
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
        <div>{{film.vote_average}}</div> 
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

        }
    },
}
</script>

<style scoped lang="scss">
.lang_img {
    height: 10px;
    width: 18px;
}
</style>