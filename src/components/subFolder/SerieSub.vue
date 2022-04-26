<template>
    <div class="p-3"> 
        <div>{{serie.name}}</div>
        <div>{{serie.original_name}}</div>
        <div v-if='serie.original_language == "en" '>
            <img src="../../assets/img/Flag_of_the_United_Kingdom.svg" alt="en" class="lang_img">
        </div>
        <div v-else-if='serie.original_language == "it" '>
            <img src="../../assets/img/Flag_of_Italy.svg" alt="it" class="lang_img">
        </div>
        <div v-else-if='serie.original_language == "ja" '>
            <img src="../../assets/img/Flag_of_Japan.svg" alt="jp" class="lang_img">
        </div>
        <div v-else>
            {{serie.original_language}}
        </div>
        <div>{{serie.vote_average}}</div>
    </div>
</template>

<script>
export default {
    name: 'MovieSub',
    props: {
        serie: Object,
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