<template>
    <div>
        <h2>film</h2>
        <div class="d-flex justify-content-center flex-wrap">
            <MovieSub v-for="(element, index) in querySaveArrayMovies" :key="index" :film="element"/>
        </div>

        <h2>serie</h2>
        <SerieSub v-for="(element, index) in querySaveArraySeries" :key="index" :serie="element"/>
    </div>
</template>

<script>
import MovieSub from './subFolder/MovieSub.vue';
import SerieSub from './subFolder/SerieSub.vue';

export default {
    name: 'MainComp',
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
div {
    h2 {
        text-transform: uppercase;
    }
}
</style>
