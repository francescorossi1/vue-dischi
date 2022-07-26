<template>
    <div class="my-5">
        <div class="container">
            <div class="album-list row row-cols-5 m-auto justify-content-center g-4">
                <div class="col album-card" v-for="album in albums" :key="album.title">
                    <figure class="p-3 h-100">
                        <img :src="album.poster" :alt="album.title" class="img-fluid mb-3">
                        <figcaption class="h-100 text-center">
                            <h5 class="mb-3 text-white">{{ album.title.toUpperCase() }}</h5>
                            <div class="text-muted">{{ album.author }}</div>
                            <div class="text-muted">{{ album.year }}</div>
                        </figcaption>
                    </figure>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import axios from 'axios'
export default {
    name: "MainContent",
    data() {
        return {
            albums: []
        }
    },
    created() {
        axios.get('https://flynn.boolean.careers/exercises/api/array/music').then((res) => {
        this.albums = res.data.response
    })}

}
</script>

<style lang="scss">
@import '../assets/sass/vars';

.album-card figure {
    background-color: $primary_color;
}
</style>