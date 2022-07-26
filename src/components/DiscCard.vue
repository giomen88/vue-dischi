<template>
    <div class="container py-5 d-flex justify-content-between align-items-center flex-wrap">
        <div class="disc-card d-flex flex-column justify-content-between p-4 text-center"
        v-for="disc in discs"
        :key="disc.title">
            <img :src="disc.poster" :alt="disc.title" class="img-fluid mb-3">
            <h5 class="text-white">{{ disc.title.toUpperCase() }}</h5>
            <p class="text-secondary fs-4">{{ disc.author }}</p>
            <p class="text-secondary fs-5">{{ disc.year }}</p>
        </div> 
    </div>
</template>

<script>
import axios from 'axios'

export default {
    name: 'DiscCard',
    components: {

    },
    data() { return {
        discs: [],
    }},
    mounted() {
        axios.get('https://flynn.boolean.careers/exercises/api/array/music')
        .then((res) => {
            this.discs = res.data.response;
            console.log(this.discs);
        })
    }
}
</script>

<style lang="scss" scoped>
@import '../assets/sass/vars';
.disc-card {
    margin: 10px;
    flex-basis: calc(20% - 20px);
    min-height: 450px;
    background-color: $bg-secondary;
}
</style>