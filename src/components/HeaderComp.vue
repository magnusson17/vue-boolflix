<template>
    <div class="d-flex justify-content-between align-items-center p-4">
        <div class="d-flex">
            <h2 class="color_dc3545">Netflean</h2>
            <div class="dropdown mx-3">
                <button class="btn btn-secondary dropdown-toggle text-capitalized" type="button" id="dropdownMenuButton1" data-bs-toggle="dropdown" aria-expanded="false">
                    generi
                </button>

                <ul class="dropdown-menu" aria-labelledby="dropdownMenuButton1">
                    <li><a class="dropdown-item" href="#">Action</a></li>
                    <li><a class="dropdown-item" href="#">Another action</a></li>
                    <li><a class="dropdown-item" href="#">Something else here</a></li>
                </ul>
            </div>
        </div>

        <div class="d-flex">
            <input type="text" v-model="querySon" @keydown.enter.prevent="$emit('queryFunSon', querySon)">
            <!-- emit per portare una funz da padre a figlio -->
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