<template>
    <div class="d-flex justify-content-between align-items-center p-4">
        <div>
            <h2 class="color_dc3545">Netflean</h2>
        </div>

        <div class="d-flex">
            <input type="text" v-model="querySon" @keydown.enter.prevent="$emit('queryFunSon', querySon)">
            <button @click.prevent="$emit('queryFunSon', querySon)" type="button" class="btn btn-danger mx-3">cerca</button>
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
div {
    button {
        text-transform: capitalize;
    }
}

.color_dc3545 {
    color: #dc3545;
}
</style>