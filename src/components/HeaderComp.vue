<template>
    <div class="d-flex justify-content-between align-items-center p-4">
        <div>
            <img src="" alt="img">
        </div>

        <div>
            <input type="text" v-model="query">
            <button @click="$emit('queryFun', query)">cerca</button>
        </div>
    </div>
</template>

<script>
export default {
    name: 'HeaderComp',
    
    data() {
        return {
            query: ''
        }
    },
}
</script>

<style scoped lang="scss">

</style>