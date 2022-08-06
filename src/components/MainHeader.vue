<template>
    <header>
        <nav class="nav px-4 d-flex justify-content-between align-items-center">
            <img src="../assets/img/spotify.png" alt="spotify logo">
            <div>
                <BaseSelect @set-option="sendOption" :genres-list="genresList" />
            </div>
        </nav>
    </header>
</template>

<script>
import BaseSelect from './BaseSelect.vue'
export default {
    name: "MainHeader",
    props: { genresList: Array },
    components: { BaseSelect },
    methods: {
        sendOption(value){
            this.$emit('send-option', value)
        }
    }
}
</script>

<style lang="scss" scoped>
@import '../assets/sass/style.scss';

header {
    background-color: $primary_color;

    .nav {
        height: 70px;

        img {
            height: 50px;
            width: 50px;
        }
    }
}
</style>