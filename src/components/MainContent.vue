<template>
    <div class="my-5">
        <div class="container">
            <div v-if="!isLoading" class="album-list row row-cols-5 m-auto justify-content-center g-4">
                <AlbumCard v-for="album in albums" :key="album.title" :albumDetails="album" />
            </div>
            <div class="text-center h2 text-white" v-else>Album in caricamento...</div>
        </div>
    </div>
</template>

<script>
import axios from 'axios'
import AlbumCard from './AlbumCard'
export default {
    name: "MainContent",
    components: { AlbumCard },
    data() {
        return {
            albums: [],
            isLoading: false
        }
    },
    created() {
        this.isLoading = true;
        axios.get('https://flynn.boolean.careers/exercises/api/array/music').then((res) => {
            this.albums = res.data.response
            this.isLoading = false
        })
    }

}
</script>

<style lang="scss">
@import '../assets/sass/vars';

.album-card figure {
    background-color: $primary_color;
}
</style>