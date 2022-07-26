<template>
    <header>
        <nav class="nav p-2">
            <img src="../assets/img/spotify.png" alt="spotify logo">
        </nav>
    </header>
</template>

<script>
export default {
    name: 'MainHeader'
}
</script>

<style lang="scss" scoped>
@import '../assets/sass/vars';

.nav {
    height: 70px;
    background-color: $primary_color;

    img {
        height: 50px;
        width: 50px;
    }
}
</style>