<template>
    <div class="my-5">
        <div class="container">
            <div v-if="!isLoading" class="album-list row row-cols-5 m-auto justify-content-center g-4">
                <AlbumCard v-for="album in filteredAlbums" :key="album.title" :albumDetails="album" />
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
    props: { selectedOption: String },
    data() {
        return {
            albums: [],
            genres: [],
            isLoading: false,
        }
    }, computed: {
        filteredAlbums() {
            if (!this.selectedOption) return this.albums
            else return this.albums.filter((album) => {
                return album.genre === this.selectedOption
            })

        }
    }, methods: {
        getGenre() {
            this.albums.map((album) => {
                if (!this.genres.includes(album.genre)) {
                    this.genres.push(album.genre)
                }
            })
        }
    },
    created() {
        this.isLoading = true;
        axios.get('https://flynn.boolean.careers/exercises/api/array/music').then((res) => {
            this.albums = res.data.response;
            this.isLoading = false;
            this.getGenre()
            this.$emit('get-data', this.genres)
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