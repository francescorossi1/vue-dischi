<template>
    <header>
        <nav class="nav px-4 d-flex justify-content-between align-items-center">
            <img src="../assets/img/spotify.png" alt="spotify logo">
            <div>
                <select id="base-select" class="form-select" v-model="optionValue" @change="$emit('set-option', optionValue)">
                    <option value="Default">Seleziona un genere</option>
                    <option value="Rock">Rock</option>
                    <option value="Pop">Pop</option>
                    <option value="Jazz">Jazz</option>
                    <option value="Metal">Metal</option>
                </select>
            </div>
        </nav>
    </header>
</template>

<script>
export default {
    name: 'MainHeader',
    data(){
        return {
            optionValue: ''
        }
    }
}
</script>

<style lang="scss" scoped>
@import '../assets/sass/style.scss';

header {
    background-color: $primary_color;
    .nav{
    height: 70px;
    img {
        height: 50px;
        width: 50px;
    }
    }
}
</style>