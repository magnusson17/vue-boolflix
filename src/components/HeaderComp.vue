<template>
    <div class="d-flex justify-content-between align-items-center p-4">
        <div>
            <img src="" alt="img">
        </div>

        <div>
            <input type="text" v-model="querySon" @keydown.enter.prevent="$emit('queryFunSon', querySon)">
            <button @click.prevent="$emit('queryFunSon', querySon)">cerca</button>
        </div>
    </div>
</template>

<script>
export default {
    name: 'HeaderComp',
    
    data() {
        return {
            querySon: ''
        }
    },
}
</script>

<style scoped lang="scss">

</style>