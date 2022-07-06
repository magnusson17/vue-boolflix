<template>
    <div>
        <div class="container p-3 text-uppercase text-white">
            <h2>film</h2>
        </div>
        <div class="container">
            <div class="row row-cols-lg-4 row-cols-md-3 row-cols-sm-2 row-cols-xs-1 g-2">
                <MovieSub v-for="(element, index) in querySaveArrayMovies" :key="index" :film="element"/>
            </div>
        </div>

        <div class="container p-3 text-uppercase text-white">
            <h2>serie</h2>
        </div>
        <div class="container">
            <div class="row row-cols-lg-4 row-cols-md-3 row-cols-sm-2 row-cols-xs-1 g-2">
                <SerieSub v-for="(element, index) in querySaveArraySeries" :key="index" :serie="element"/>
            </div>
        </div>
    </div>
</template>

<script>
import MovieSub from './subFolder/MovieSub.vue';
import SerieSub from './subFolder/SerieSub.vue';

export default {
    name: 'MainComp',
    //props per portare info dal figlio al padre
    props: {
        querySaveArrayMovies: Array,
        querySaveArraySeries: Array,
    },
    components: {
        MovieSub,
        SerieSub,
    },
    
    data() {
        return {

        }
    },
}
</script>

<style scoped lang="scss">
</style>
