<template>
    <div>
        <div 
        v-for="(element, index) in queryFunSecondSon" 
        :key="index"
        class="p-3">
            <div>{{element.title}}</div>
            <div>{{element.original_title}}</div>
            <div v-if='element.original_language == "en" '>
                <img src="../assets/img/Flag_of_the_United_Kingdom.svg" alt="en" class="lang_img">
            </div>
            <div v-if='element.original_language == "ja" '>
                japooooo
            </div>
            <div v-else>
                {{element.original_language}}
            </div>
            <div>{{element.vote_average}}</div> 
        </div>
    </div>
</template>

<script>
export default {
    name: 'MainComp',
    props: {
        queryFunSecondSon: Array,
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
}
</style>
